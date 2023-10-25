Before we begin, please correct me if there is any misinformation in this article.

The article assumes you have some knowledge regarding domains, ports, HTTP, etc. Feel free to ask in the comment section below if you're missing something. 

Let's begin.

Backend servers are hosted in a single computer like a monolith in the old days. This means that the DB, the API, and other services are in one computer and share the RAM and the disk drive. Here's a general diagram of how almost all web servers are architectured:

```mermaid
flowchart TB
	subgraph clients [clients]
		desktop[[Desktop]]
		mobile[[Mobile]]
	end
	subgraph backend [backend computer]
		direction LR
		nginx[[:80/:443 Nginx reverse proxy server]]
		api[[:5000 API Server]]
		DB[[:3306 DB]]
		
		subgraph optional0 [Optional]
		direction TB
			ssr[[:3000 SSR client]]
			CRON[[:5001 CRON Service]]
		end
	end
	
	desktop & mobile <--req/res--> nginx
	nginx -./.-> ssr
	nginx --/api--> api
	ssr --req--> api
	api & CRON --> DB
```

This is your usual setup at home. 

While it will work as intended, the scalability aspect of it could be better as all the services share the computer's resources.

Then, services started having their own host machine - utilizing the network more. Something like this:

```mermaid
flowchart TB
	subgraph clients [clients]
		desktop[[Desktop]]
		mobile[[Mobile]]
	end

	subgraph network [Network]
		direction LR
		nginx[[10.0.0.2:80/:443 - Nginx reverse proxy server]]
		api[[10.0.0.3:5000 - API Server + redis]]
		DB[[10.0.0.4:3306 - DB]]
		
		subgraph optional0 [Optional]
		direction TB
			ssr[[10.0.0.5:3000 - SSR client]]
			CRON[[10.0.0.6:5001 - Service + redis]]
		end
	end

	
	desktop & mobile <--req/res--> nginx
	nginx -./.-> ssr
	nginx --/api--> api
	ssr --req--> api
	api & CRON --> DB
```

Thanks to Nginx's load-balancing capabilities, every application can scale horizontally on demand. 

Additionally, every service can have an independent caching layer via Redis, drastically improving performance.

The \[API server + redis\] service can even be broken down to microservice architecture something like this:

```mermaid
flowchart TB
	nginx[[Nginx reverse proxy server]]
	subgraph api [API Server]
		direction TB
		user[[User + redis]]
		orders[[Orders + redis]]
		expiration[[Expiration + redis]]
		message[[Event Messaging RabbitMQ/NATS streaming]]
	end
	nginx --/user-->user 
	nginx --/orders-->orders 
	nginx --/expiration-->expiration 
	user & orders & expiration <--> message
```

It's hard to have dedicated services when starting out but this is where docker really shines.

Okay, what is Docker? Docker is a platform designed to help developers build, share, and run modern applications. It utilizes OS-level virtualization to deliver software in packages called containers (via google). 

With docker, you can easily have a dedicated service which code running on a specific image. This eliminates the "it runs on my machine" problem as well!


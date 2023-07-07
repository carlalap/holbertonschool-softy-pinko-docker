# Docker

<div class="panel panel-default" id="project-description">
<div class="panel-body">
<h2>Description</h2>

<p>In this project we will create an infrastructure for an application that utilizes a reverse proxy, a load balancer, two application servers, and one front-end server.</p>
<p>Let’s consider the following design:</p>

<p><img src="https://drive.google.com/uc?id=1-OZ0gG2z__v-lACc1RwvZWMQP6GnBQ0n" alt="" loading='lazy' style="" /></p>

<h2>High-level Design</h2>

<p>In this design, there is a single server that acts as the entry point for your application. That server acts as a reverse proxy server, which routes traffic to either the API servers or the front-end static-content server; it also acts as a load balancer to balance traffic between the two API servers. When traffic comes in, the server will determine which service it needs to go to (either the front-end static-content server or the API server) and:</p>

<ul>
<li><p>If the request is to be routed to the front-end static-content server, it will do so and any static content that is returned from the front-end static-content server to the proxy server will then be sent to the client. The client isn’t directly communicating with the front-end static-content server.</p></li>
<li><p>If the request is to be routed to the API server, then it will first go through a load-balancing algorithm to determine which API server to send the request to. We will be using the basic Round Robin load-balancing algorithm for our site. Once the request is routed to an API server and the response is sent back to the proxy server, it will then be sent to the client. The client isn’t directly communicating with either of the API servers.</p>

<ul>
<li>What is Round Robin load balancing? Round Robin load balancing is a method of distributing traffic across multiple servers or nodes in a network. In this approach, the load balancer assigns requests to each server in a rotating manner, meaning that each server takes turns serving the requests. For example, if there are three servers A, B, and C, the first request will be sent to server A, the second to server B, the third to server C, the fourth to A, the fifth to B, and so on, while the cycle repeats. This ensures that each server receives an equal share of the traffic, and can prevent any one server from becoming overwhelmed with requests. Round Robin load balancing is a simple and effective way to distribute traffic, but it may not be suitable for all applications, particularly those with varying workload patterns or resource requirements. For our learning purposes in this project, it is a sufficient algorithm to implement for our load-balancing needs.</li>
</ul></li>
</ul>

<h1>What You Need Before Starting</h1>

<ul>
<li>Install Docker Desktop on your local computer (not your sandbox)

<ul>
<li>https://www.docker.com/</li>
<li>For more detailed installation instructions, see:</li>
<li><a href="/rltoken/R-4LnaCMOLb4iHip2PRzXQ" title="Windows" target="_blank">Windows</a></li>
<li><a href="/rltoken/agZxZoWSuS1k8GPGu6tgeg" title="Mac" target="_blank">Mac</a></li>
<li><a href="/rltoken/6DmPUit3nnE2rToik9hRLw" title="Linux" target="_blank">Linux</a></li>
<li><a href="/rltoken/zA7rXDO1tIr-gR3Egsz31Q" title="Chromebook" target="_blank">Chromebook</a> - Note: this is the Docker engine, but not Docker Desktop. It is unclear how well this will work on a chromebook - you may want to use a Windows, Mac, or Linux machine or a machine on campus, instead.</li>
</ul></li>
<li>Familiarize yourself with Docker

<ul>
<li><a href="/rltoken/L4XMX9Zu6osHOXUxJO_l6g" title="Docker Tutorial" target="_blank">Docker Tutorial</a></li>
</ul></li>
</ul>

  </div>
</div>


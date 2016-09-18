### quaich: A serverless microframework for event-driven Scala Programming on AWS Lambda - Brendan McAdams

Sneak preview of a scala equivalent to Amazon's [chalice](https://github.com/awslabs/chalice), 'a serverless
microframework for AWS'.

AWS Lambda provides infrastructure to run your code on that is only actually 'allocated' when your code needs to run.
In response to an incoming event (HTTP request, S3 trigger) lambda will load your code into an execution environment,
use it to process the event and then deprovision the associated resources after, thus relieving you of the obligation 
to manage the infrastructure the code runs on.

The function to be executed must implement an API supplied by AWS, and there's a fairly large amount of administrative
overhead in configuring API gateways, permissions and uploading your code. The aim of this project is to automate as
much of the grunt work as possible.

The idea of being able to write a function and then make it available on the web with a single command without the 
need to provision, configure and maintain the infrastructure it runs on is really exciting. Just not quite sure what to
do with it yet.

**Code** - https://github.com/bwmcadams/quaich


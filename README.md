# SlashDeploy Website

This repository contains code to build and deploy
[blog.slashdeploy.com](http://blog.slashdeploy.com). The site itself
is statically generated with Jekyll. There is a CloudFormation stack
to create manage the DNS, S3, Cloudfront distribution, and Route53 DNS
records. The process is coordinated through a few key files.

* `bin/website` - Cloudformation manager
* `script/ci/deploy` - Build and deploy the thing
* `script/server` - Start a development server

## Developing

	$ make check
	$ script/server # do work
	$ make test-ci

## Tests

* `make test-dist`: Ensure generated site has artifacts required
	CloudFront artifacts.
* `make test-shellcheck`: Run shell programs through shellcheck
* `make test-website`: Validate CloudFormation template

## Deploying

First ensure the `slashdeploy.com` Route53 hosted zone is ready. See
the [DNS][].

[dns]: https://gitlab.com/slashdeploy/dns

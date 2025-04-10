SHELL=/bin/bash


ruby-build:
	docker build -f Dockerfile.ruby -t cruby .

ruby:
	docker run --rm -it --name crubyt -v $(CURDIR):/data cruby bash

testcases: 
	find ./testdata -type d -exec chmod 777 {} \;
	docker run --rm -it --name crubyt -v $(CURDIR):/data cruby make

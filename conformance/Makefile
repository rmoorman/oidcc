REBAR = $(shell pwd)/rebar3
APP=oidcc

.PHONY: all ct test clean elvis compile conformance_test

all: compile

clean:
	$(REBAR) clean
	rm -f rebar.lock
	rm -rf _build

compile:
	$(REBAR) compile

run:
	$(REBAR) run


conformance_test:
	# ensure the configured versions are used by upgrading
	$(REBAR) upgrade
	$(REBAR) release
	./utils/run_tests.sh

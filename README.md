## Ignition
[![CircleCI](https://circleci.com/gh/pivotalservices/ignition/tree/master.svg?style=svg)](https://circleci.com/gh/pivotalservices/ignition/tree/master)

A landing page for developers to self-service their way onto your Pivotal Cloud Foundry (PCF) deployment(s).

* Authenticates the user via OAuth2
* Allows the user to access Apps Manager and view their personal PCF org

### Contribute

This application is a combination of a JavaScript single-page app (built with React) and a Go web app. The JavaScript app is built into a javascript bundle, that the Go web app serves up. The Go web app also provides an API that the JavaScript app uses to function.

#### Yak Shaving (Developer Setup)

This project uses [`dep`](https://github.com/golang/dep) and [`yarn`](https://yarnpkg.com) for dependency management.

Make sure you have `dep` and `yarn` installed, and then run:

> `curl -o- https://raw.githubusercontent.com/pivotalservices/ignition/master/setup.sh | bash`

Don't just blindly execute shell scripts though, take a look at it and feel free to download it locally and run it after thorough inspection.

#### Add A Feature / Fix An Issue

We welcome pull requests to add additional functionality or fix issues. Please follow this procedure to get started:

1. Ensure you have `go` `>=1.10.x` and `node` `v8.x.x` installed
1. Ensure your `$GOPATH` is set; this is typically `$HOME/go`
1. Clone this repository: `go get -u github.com/pivotalservices/ignition`
1. Go to the repo root: `cd $GOPATH/src/github.com/pivotalservices/ignition`
1. *Fork this repository*
1. Add your fork as a new remote: `git remote add fork https://github.com/INSERT-YOUR-USERNAME-HERE/ignition.git`
1. Create a local branch: `git checkout -b your initials-your-feature-name` (e.g. `git checkout -b jf-add-logo`)
1. Make your changes, ensure you add tests to cover the changes, and then validate that all changes pass (see `Run all tests` below)
1. Push your feature branch to your fork: `git push fork your initials-your-feature-name` (e.g. `git push fork jf-add-logo`)
1. Make a pull request: `https://github.com/pivotalservices/ignition/compare/master...YOUR-USERNAME-HERE:your-initials-your-feature-name`

### Run the application locally

1. Make sure you're in the repository root directory: `cd $GOPATH/src/github.com/pivotalservices/ignition`
1. Ensure the web bundle is built: `pushd web && yarn build && popd`
1. Start the go web app: `go run cmd/ignition/main.go`
1. Navigate to http://localhost:3000

### Run all tests

1. Make sure you're in the repository root directory: `cd $GOPATH/src/github.com/pivotalservices/ignition`
1. Run go tests: `go test ./...`
1. Run web tests: `pushd web && yarn ci && popd`

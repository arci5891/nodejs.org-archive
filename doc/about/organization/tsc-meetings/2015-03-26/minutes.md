# Minutes for the Node.js core team meeting of 03/26/2015

## Participants

* Alexis Campailla
* Colin Ihrig
* James Snell
* Julien Gilli
* Michael Dawson
* Robert Kowalski
* TJ Fontaine
* Trevor Norris
* Wyatt Preul

## Discussions

### Foundation charter

TJ: We want to make sure that we're participating in this process.

TJ: Now could be a good time for everyone to talk about tools they know that
would work well to help the work done by the foundation.

### Benchmarks

Michael: We'd like to have tools to make sure there's no performance
regression between releases.

Michael: We could use https://github.com/acmeair/acmeair, and there's a
Node.js version: https://github.com/acmeair/acmeair-nodejs.

Michael: Have talked to maintainer of acme-air and they are willing to
collaborate, we could also get them to give us an intro to the benchmark if
that makes sense.

TJ: We also want a benchmark specifically for low-latency and high
concurrency.

TJ: How do we want to start with that? Also should assess what we already have.

Michael: Might want to form a performance working group.

Michael: Good idea to reach out to io.js too.

TJ to forward to Michael contacts at Yahoo, Netflix and Paypal that might be
interested in participating.

### OOB OSX

v0.10.37 fixed an issue in kqueue regarding out of band data. The reporter
never heard back from Apple, and no CVE  has been assigned. Could lead to a
DOS scenario.

### Security issue in vm.js

TJ: Got an email about a user concerned about the fact that the parent of a
sliced buffer can be traversed across VMs.

Trevor: this has been known for a while.

TJ: sandbox is a not a security context sandbox, but more a "programming
sandbox".

TJ: In my opinion, mostly a documentation bug on our part.

### Putting a link to IBM Node.js SDK on nodejs.org

TJ: I don't have any objection. What link would we use?

James: We have a landing page for this SDK for Node.js. Easiest thing would be
to land to this page.

TJ: I want to avoid confusion if the versions are not in sync between the two
projects.

James: We can make it clear on this landing page.

TJ: Can the additional debugging stuff be upstreamed?

Michael: We want to make that available, maybe via npm. Same for IDDE.

TJ: Would be great to have the additional debugging support in the code base
too, so that people can load core files from z platforms and do debugging.

## Releases

### v0.10.38

Julien: Would be great to document how to upgrade OpenSSL.

James: Had an item in my todo list to do that.

Julien: We can team up to do that.

TJ: I would suggest to start shipping an alternate binary linked with shared
dynamic libraries for libuv, OpenSSL, etc.

TJ: Might be difficult to do that for dependencies where we have floating
patches.

### v0.12.2

Julien: New P-1 issue added: debugger is very slow, takes 1 or 2 minutes to do
basic operations, see https://github.com/joyent/node/issues/9125 for more
information.

Trevor: There's a major issue with buffer
(https://github.com/joyent/node/issues/9180) that causes asserts for a lot of
users, can we get a v0.12.2 release asap with the current state of v0.12, and
move everything else from the 0.12.2 milestone to 0.12.3?

Julien: We may also want to add an upgrade to npm 2.7.3 for this release.

Trevor: See also https://github.com/joyent/node/issues/14165.

No objection from anyone.

## Tool for testing npm modules

James: Currently porting from Python to Node.js. Will put in a separate repo.
Some issues regarding non-uniform tests output and additional npm
dependencies.

## Discussions with PM2 developers

TJ: Met recently with developers from PM2. Would like to have a discussion
with them around potential improvements to the cluster module.

## Crypto performance

James: Interested in getting some work to propose enhancements to crypto
performance. What do you think about adding async mechanisms to crypto?

TJ: Could have a discussion of what we'd like as an async API. Could also
broaden the discussion to a long term goal of having better TLS performance.
That will be even more important with HTTP/2.

James: Can start the conversation with a proposal of improvements.

## Website

TJ: We'll have a new single certificate with support for subdomains.

Robert: Need some feedback on https://github.com/joyent/node-
website/issues/81.

Robert: Made changes to the license here: https://github.com/joyent/node-
website/pull/93.

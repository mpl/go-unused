# unused

_unused_ checks Go code for unused constants, variables, functions and
types.

## Install

	go get honnef.co/go/unused/cmd/unused

## Usage

	unused -help

## Examples

```
$ time unused cmd/go
/usr/lib/go/src/cmd/go/generate.go:375:21: identLength is unused
/usr/lib/go/src/cmd/go/testflag.go:278:6: setIntFlag is unused
/usr/lib/go/src/cmd/go/pkg.go:688:2: toRoot is unused
/usr/lib/go/src/cmd/go/get.go:513:6: cmpGoVersion is unused
/usr/lib/go/src/cmd/go/main.go:406:5: logf is unused
/usr/lib/go/src/cmd/go/main.go:431:6: runOut is unused
/usr/lib/go/src/cmd/go/build.go:1327:6: hasString is unused
/usr/lib/go/src/cmd/go/build.go:2328:6: toolVerify is unused
./unused cmd/go  3.38s user 0.23s system 451% cpu 0.801 total
```

```
$ time unused $(go list github.com/prometheus/prometheus/... | grep -v /vendor/)
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/scrape.go:41:2: ingestedSamplesCap is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/scrape.go:49:2: errSkippedScrape is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/target.go:186:18: report is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/discovery/serverset.go:33:2: serversetNodePrefix is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/discovery/dns.go:39:2: interval is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/retrieval/discovery/nerve.go:31:2: nerveNodePrefix is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/remote/opentsdb/client.go:40:2: illegalCharsRE is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:86:34: add is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:197:34: clone is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:204:34: firstTime is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:224:34: marshal is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:241:34: marshalToBuf is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/doubledelta.go:281:34: encoding is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:79:28: add is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:191:28: clone is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:198:28: firstTime is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:216:28: marshal is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:233:28: marshalToBuf is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/storage/local/delta.go:273:28: encoding is unused
/home/dominikh/prj/src/github.com/prometheus/prometheus/promql/parse.go:968:8: ctx is unused
./unused -v $(go list github.com/prometheus/prometheus/... | grep -v /vendor/  5.17s user 0.42s system 566% cpu 0.989 total
```

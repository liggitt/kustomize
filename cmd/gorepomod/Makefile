MYGOBIN := $(shell go env GOPATH)/bin

$(MYGOBIN)/gorepomod: usage.go
	go install .

.PHONY: test
test: $(MYGOBIN)/gorepomod
	go test ./...

usage.go: README.md $(MYGOBIN)/goimports
	go generate . \
	$(MYGOBIN)/goimports -w usage.go

$(MYGOBIN)/goimports:
	go install golang.org/x/tools/cmd/goimports

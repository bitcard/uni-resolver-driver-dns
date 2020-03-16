![DIF Logo](https://raw.githubusercontent.com/decentralized-identity/universal-resolver/master/docs/logo-dif.png)

# Universal Resolver Driver: dns

This is a [Universal Resolver](https://github.com/decentralized-identity/universal-resolver/) driver for **DNS** identifiers.

## Specifications

* [Decentralized Identifiers](https://w3c.github.io/did-core/)
* [The Decentralized Identifier (DID) in the DNS](https://datatracker.ietf.org/doc/draft-mayrhofer-did-dns/)

## Example Identifiers

```
ssi.labs.nic.at
```

## Build and Run (Docker)

```
docker build -f ./docker/Dockerfile . -t universalresolver/driver-dns
docker run -p 8080:8080 universalresolver/driver-dns
curl -X GET http://localhost:8080/1.0/identifiers/ssi.labs.nic.at
```

## Build (native Java)

 ### Configuration
 For downloading the dependencies of this project a Personal Access Token for GitHub must be configured in file [resolver/java/settings.xml](https://github.com/decentralized-identity/uni-resolver-driver-dns/blob/release-0.1.x/settings.xml) according to [Creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line).
 
 ### Build (native Java)
 
 Maven build:
 
 	mvn --settings settings.xml clean install

## Driver Environment Variables

The driver recognizes the following environment variables:

### `uniresolver_driver_dns_dnsServers`

 * Specifies a semicolon-separated list of DNS servers to use for lookups.
 * Default value: (empty string)

## Driver Metadata

The driver returns the following metadata in addition to a DID document:

* `did`: A DID that was found for the given DNS identifier.

# Definitions

## Application Server

This is the server that hosts the application.

## End User Application

This is the application used by the end user to connect to the [Application Server](#application-server) and to interact with it.

## Push Message

This is the content that the [Application Server](#application-server) 
wants to send to the [end user Application](#end-user-application).

## Push System

This is the whole system used to deliver the [push messages](#Push-Message) 
from the [Application Server](#application-server) 
to the [end user Application](#end-user-application).

## Application Push Protocol
Or Application Server Protocol

This is the protocol the application server uses to send [push messages](#push-message). 

## Push Gateway
Or Gateway

If the [application push protocol](#application-push-protocol) and the [Provider Receiving Protocol](#provider-receiving-protocol) are the same, and the [Application Server](#application-server) can reach the [Push Provider](#push-provider), then the gateway is not necessary.

If this is not the case the Push Gateway is needed for conversion and/or proxieing. 
The [application server](#application-server) sends [push messages](#push-message) via the [application push protocol](#application-push-protocol) to the Push Gateway for conversion to the [Provider Receiving Protocol](#provider-receiving-protocol).

If the application server can not reach the push provider the Push Gateway can also act as a normal Proxy, even if the [application push protocol](#application-push-protocol) and the [Provider Receiving Protocol](#provider-receiving-protocol) are the same.

## Provider Receiving Protocol

This is the protocol the [Push Provider](#push-provider) uses to receive [push messages](#push-message).

## Provider Push Protocol

This is the protocol the [Push Provider](#push-provider) uses to send [push messages](#push-message) to the [Distributor Application](## Distributor Application).

## Distributor Receiving Protocol

This is the protocol the [Distributor Application](#distributor-application) 
uses to recive [push messages](#push-message) from the [Push Provider](#push-provider). 
So it is the same as the [Provider Push Protocol](#provider-push-protocol), 
except if the [Distributor Application](#distributor-application) 
acts as the [Push Provider](#push-provider), 
then there is no [Provider Push Protocol](#provider-push-protocol) 
and this is just the [Provider Receiving Protocol](#provider-receiving-protocol).

## Rewrite Proxy

If the Provider Receiving Protocol needs anything else than the URI and a GET parameter to identify the end user application (eg. header, POST parameter) or need a special structure for POST data, then a rewrite proxy is used to convert the identifier in a URI or in a GET parameter and to forge the POST parameter content structure.

The rewrite proxy is application independant and provider dependant.

## Push Provider
Or Provider
Or Push Notification Provider

This is the server that listen for incoming push messages using its provider receiving protocol and forward it to the connected phone using the provider push protocol.

## Distributor Application
Or Distributor

This is the application that forwards push messages to the registered end user application. It is the application which is connected to the push provider.

## Connector Library
Or Connector
Or UnifiedPush Library

This is the library used by the end user application to register for push notifications to the distributor applicaton and to receive push messages forwarded from the ditributor application.

## Endpoint

This is the URL of the rewrite proxy (if there is one, of the push provider else) where push messages are sent for a specific end user application, from the gateway.


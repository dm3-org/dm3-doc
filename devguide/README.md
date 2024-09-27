# Developer Guide

This document will help you set up and run various DM3 services locally to create a fully decentralized messaging experience. The DM3 protocol is designed to provide seamless and secure messaging functionalities for decentralized applications (dApps) on the Ethereum blockchain, supporting use cases such as in-app communication, customer support, and contact management.

## Overview

The DM3 ecosystem consists of several key components that work together to provide a decentralized messaging platform:

1. **Frontend ( DM3 widget)**: A user interface built that integrates the DM3 widget with your frontend application, enabling messaging functionality in dApps.
2. **Delivery service**: Handles the delivery of messages between users, ensuring secure and efficient communication.
3. **Backend service**: Manages data storage and processing required for the messaging system.
4. **Resolver**: Ensures proper resolution of ENS (Ethereum Name Service) domains associated with the dm3 messaging service.

While you can use the DM3 Widget without setting up all the services locally (since the widget can interact with pre-configured hosted services), setting up your own DM3 services allows you to have a fully decentralized, self-hosted messaging system under your control. This guide will walk you through the steps required to set up each of these components.

## Prerequisites

Before setting up any of the DM3 services, ensure you have the following tools installed:

* **Docker**: Required for running the backend, delivery service, and resolver in isolated containers.
* **Docker compose**: To orchestrate multi-container Docker applications.
* **ENS domain access**: You need access to an Ethereum account with control over a valid ENS domain for setting up the delivery service and resolver.
* **RPC URL:** You need a valid RPC URL from a provider like Infura or Alchemy to connect to the Ethereum network.

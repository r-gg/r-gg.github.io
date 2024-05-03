---
layout: page
title: Secure distributed email service with Java RMI 
description: Distributed Systems course project
img: assets/img/vs-ue/vs-ue.jpg
# redirect: https://unsplash.com
importance: 3
category: software development
---

**Keywords:** *distributed systems, dns-server, java rmi, email service, secure communication, SMTP, IMAP*

## Co-authors:

Implemented this project together with my colleagues:
- Nikolaus-Mathias Herl
- Nikolaus Walther

as a part of Distributed Systems course at TU Wien.

## Summary

Implemented a decentralized E-Mailing service, that supports custom mail transfer and mail access protocols with RSA-AES-based handshake and hash-based integrity checks. 

> Code available in the [GitHub repository](https://github.com/r-gg/vs-ue).

## Implementation Details

### Decentralized Email Service

There are four types of servers: **nameservers**, **mailbox servers**, **transfer server** and **monitoring server**. Each nameserver has registry of IP addresses of the mail server of this domain and name servers of its subdomains. Mailbox servers store the messages of the users belonging to their domain/subdomain and offer access to these message. Transfer server forwards messages to the respective mailbox servers. After transfering a message, the transfer server sends a usage UDP packet (containing hosts IP & port, and senders email address) to the monitoring server. Monitoring server aggregates metrics across the transfer servers and across email addresses.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vs-ue/decentralized_naming_service.png" title="DNS" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Registration of new domains is performed with **Java RMI** recursively, i.e. each server passes the registration onto its respective subdomain servers. To address the bootstrapping problem, a **centralized registry** with the address of the root nameserver is used. See the diagram below for an illustration of registering new name- and mailbox servers.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vs-ue/register_nameserver.png" title="Nameserver registration" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vs-ue/register_mailbox.png" title="Mailbox server registration" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Security

**Mail client** is the component that allows the users to send emails and view emails via CLI. To read messages privately the client can establish an encrypted connection to the mailbox server based on an **RSA + symmetric AES handshake protocol**.

The messages that are sent to the transfer server for forwarding are already encrypted with the transfer server's public key. To ensure **message integrity**, each client can sign and verify the integrity of the message using **hash-based message authentication codes (HMAC)**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vs-ue/mail_client.png" title="Mail Client workflow" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
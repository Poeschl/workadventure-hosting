# Workadventure Self-Hosted

I couldn't find compose files that are really working out of the box for a self-hosted [Workadventure](https://github.com/thecodingmachine/workadventure) setup.
So this repository will serve me as an stable setup for my needs.

## Setup

The setup contains two docker-composes for two hosts.
This is already the minimal setup, since the turn server needs the ports 80 and 443 to be buisness-firewall safe.

For a deployment create your own `.env` file from the template and fill in your values.
After that copy the `.env` file and one of the docker-compose file to one host and the `.env` and the other docker-compose to the second.
Make sure to also transfer the `ejaberd.template.yaml` to the host which runs the workadventure system.
Start both and the workadventure should be running under your domains (you should register them beforehand).

## Jitsi

This repository will not handle the install of an Jitsi server.
So if you are low-profile you can use a trusted one and insert the url into the `.env` file.
For larger group we recommend hosting an own. The instructions for that are [here](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker/).

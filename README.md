*This project has been created as part of the 42 curriculum by yesoytur.*

# NetPractice

## Description

NetPractice is a 42 networking project. No code, just a series of broken network diagrams that you have to fix by filling in IPs, masks and routing entries until everything talks to each other. The goal is to get comfortable with TCP/IP addressing, subnetting, default gateways, and basic routing.

## Instructions

From the repo root:

```sh
./run.sh
```

If `run.sh` doesn't work, just serve the folder yourself:

```sh
python3 -m http.server 49242
```

Then open `http://localhost:49242` in your browser.

Enter your intranet login (so the configs match your evaluation), pick **Training**, and solve each level. For every level, hit **Get my config** and save the file as `levelN.json` at the repo root. The 10 exported JSON files (`level1.json` through `level10.json`) are what gets evaluated — they must all sit at the repo root.

During defense you'll have to redo three random levels in a limited time, with no external tools (a basic calculator like `bc` is the most you're allowed).

## Levels

- **Level 1** — Two hosts on the same network. Just pick compatible IPs.
- **Level 2** — Same idea, but now you also have to set a subnet mask so two of the hosts end up in the same subnet.
- **Level 3** — A switch shows up. Switches don't have IPs, and everything plugged into them shares one subnet.
- **Level 4** — First router. Two subnets connected through it, with a `/28` mask to play with.
- **Level 5** — Default gateway. A host can't reach another subnet without one.
- **Level 6** — Default route on the router (`0.0.0.0/0`) and traffic going out to "the internet".
- **Level 7** — Multiple routers chained together with `/30` point-to-point links between them.
- **Level 8** — Bigger topology with several subnets, default routes everywhere, and a more specific static route on one router.
- **Level 9** — Two separate networks behind different routers, plus internet routing with explicit static routes for each network.
- **Level 10** — The full picture: multiple subnets, a `/30` link between routers, and supernet aggregation (`/20`) on the internet side.

## Resources

Concepts you actually need to know to get through this:

- **TCP/IP addressing** — how an IP + mask defines a network and a host part.
- **Subnet masks and CIDR** — `/24`, `/28`, `/30`, etc., and how to figure out the usable host range, network address, and broadcast.
- **Default gateways** — why a host can't leave its own subnet without one.
- **Routers and switches** — switches stay inside one subnet, routers move between them.
- **Static and default routes** — `0.0.0.0/0` for "everything else", more specific prefixes when you need to steer traffic.
- **OSI layers** — at least enough to know where IP, Ethernet, and switching/routing sit.

Things I read while doing this:
- Cisco's "IP Addressing and Subnetting for New Users" article.
- The Wikipedia pages on CIDR, subnetwork, and default gateway.
- A subnet calculator (only outside of evaluation) to sanity-check ranges.

### About AI use

This README was written with the help of AI (Claude), based on my own notes and the level configs in this repo. I also used AI as a study aid while learning subnetting — mostly to check my mask math and to walk through why a given route was or wasn't matching. I did not use AI to solve the levels for me; the configs in `levelN.json` are the ones I actually filled in through the interface.

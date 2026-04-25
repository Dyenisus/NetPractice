*This project has been created as part of the 42 curriculum by yesoytur.*

# NetPractice

NetPractice is a 42 networking project. No code, just a series of broken network diagrams that you have to fix by filling in IPs, masks and routing entries until everything talks to each other.

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

## Running it

```sh
./run.sh
```

If that fails, just serve the folder yourself:

```sh
python3 -m http.server 49242
```

Then open `http://localhost:49242`.

For each level, solve it in the interface, hit **Get my config**, and save the file as `levelN.json` at the repo root.

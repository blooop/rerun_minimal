This is a (almost) minimal example of using [pixi](https://github.com/prefix-dev/pixi/) to run some code with [rerun.io](https://rerun.io/)

It is not minimal because it supports multiple python versions, but that is quite common for my workflows. 

## usage

```
$ pixi run demo
```

## output

The demo will fail to install rerun-sdk

```
  × failed to solve the pypi requirements of 'py310' 'linux-64'
  ├─▶ failed to resolve pypi dependencies
  ╰─▶ Because rerun-sdk==0.18.2 has no wheels with a matching platform tag and only rerun-sdk<=0.18.2
      is available, we can conclude that rerun-sdk>=0.18.2 cannot be used.
      And because you require rerun-sdk>=0.18.2, we can conclude that your requirements are
      unsatisfiable.

```

## Solution

uncommenting these lines

```
# [tool.pixi.dependencies]
# rerun-sdk = ">=0.18.2"
```

and running the demo again will work. 
# helmfile-statevalue-key1  


Run w/ helmfile 0.80.0

This:
```
./helmfile --log-level debug \
  --state-values-set top.middle.x='x1',top.middle.y='y1' \
  --file helmfile.works.yaml template
```

or this:
```
./helmfile --log-level debug \
  --state-values-set top.middle.x='x1' \
  --state-values-set top.middle.y='y1' \
  --file helmfile.works.yaml template
```

I get:
```
second-pass rendering result of "helmfile.works.yaml.part.0":
 0: releases:
 1:   - name: nginx-1
 2:     chart: stable/nginx-ingress
 3:     values:
 4:
 5:       - key-x: "exists"
 6:
 7:         x: x1
 8:         y: <no value>
 9:
```

I expect `y: y1` and `key-y: "exists"` but they are missing

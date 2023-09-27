# pgo-profiles

The `default.iprof` file is made as follows:

```
script/uberjar && script/compile --pgo-instrument
./bb -e '(time (loop [val 0 cnt 100000000] (if (pos? cnt) (recur (inc val) (dec cnt)) val)))'
```

Then this `default.iprof` file is uploaded to Github releases and used over multiple builds.

This speeds up the loop example with about 2-3x.

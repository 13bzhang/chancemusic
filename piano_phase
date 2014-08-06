# Reich Piano Phase

# Piano 1
def f(n)
  use_synth "dull_bell"
  play_pattern_timed [64,66,71,73,74,65,64,72,71,65,74,72], [0.3]
end

# Piano 2
def g(i)
  use_synth "dull_bell"
  play_pattern_timed [64,66,71,73,74,65,64,72,71,65,74,72], [i]
end

in_thread do
  30.times do
    f 60
  end
  sleep 0.29
end

n=0.30

in_thread do
  g n
  g n
  28.times do
    g n-0.005
  end
  sleep 0.29
end

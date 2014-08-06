# John Cage-esque I Ching "Music Change" Function

def iching(n)
  def yarrow(r)
    if r==1
      s=1
    elsif r>1 && r<7
      s=1
    elsif r>6 && r<14
      s=0
    else
      s=0
    end
    return s
  end
  y1 = 1*(yarrow rrand_i(1,16))
  y2 = 10*(yarrow rrand_i(1,16))
  y3 = 100*(yarrow rrand_i(1,16))
  a = y1+y2+y3
  if a==111
    play 1+n
  elsif a==110
    play 2+n
  elsif a==101
    play 3+n
  elsif a==100
    play 4+n
  elsif a==11
    play 5+n
  elsif a==10
    play 6+n
  elsif a==1
    play 7+n
  else
    play 8+n
  end
end

# example
in_thread do
  use_synth "dull_bell"
  play 74
  sleep 0.25
  play 74
  sleep 0.25
  10.times do
    4.times do
      iching 70
      sleep 0.25
    end
    4.times do
      iching 70
      sleep 0.50
    end
  end
  play 74
end

in_thread do
  use_synth "dull_bell"
  sleep 0.25
  play 76
  sleep 0.25
  play 76
  10.times do
    4.times do
      iching 70
      sleep 0.50
    end
    4.times do
      iching 70
      sleep 0.25
    end
  end
  play 74
end

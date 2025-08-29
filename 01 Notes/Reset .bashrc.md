# Fully Reset .bashrc to Ubuntu Default
#bash
```bash
cp /etc/skel/.bashrc ~/.bashrc
source ~/.bashrc
```

eval "$(oh-my-posh init bash --config ~/atomicBit.omp.json)"
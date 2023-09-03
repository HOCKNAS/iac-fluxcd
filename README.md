ssh-keygen \
    -m PEM \
    -t rsa \
    -b 4096 \
    -C "support@hocknas.us" \
    -f /Users/hocknas/iac-fluxcd/demo-fluxcd

flux bootstrap git \
  --url=ssh://git@github.com/HOCKNAS/iac-fluxcd.git \
  --branch=master \
  --private-key-file=/Users/hocknas/iac-fluxcd/demo-fluxcd  \
  --path=clusters/dev
  
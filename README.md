To reproduce:
```
python -m venv .venv
source .venv/bin/activate
pip install ansible
ansible-playbook -i localhost run.yml
ansible-playbook -i localhost break.yml
```

expectation: Handler also gets called during break.yml-run


If you import a role twice the 2nd import can prevent the handlers notified
during the first import to run.

In this example the 2nd import is conditional on "true == false", that never
happens, therefore mask.yml is never executed.

Yet during the handler-phase the handler is ignored because that conditional
fails.

To reproduce:
```
python3 -m venv .venv
source .venv/bin/activate
pip install ansible
ansible-playbook -i localhost run.yml
ansible-playbook -i localhost break.yml
```

expectation: Handler also gets called during break.yml-run


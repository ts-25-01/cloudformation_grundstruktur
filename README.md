## Anleitung zum Nachbauen des Webserver-Beispiels

## Template anlegen
- webserver.yaml ist angelegt
- das ist alles drin, was wir brauchen
- korrekt (überprüft)

## CloudFormation Template validieren
```bash
aws cloudformation validate-template --template-body file://webserver.yaml
```
Wenn wir eine Ausgabe bekommen, die etwas mit Properties und Description enthält, alles gut!

## CloudFormation Stack anlegen
```bash
aws cloudformation create-stack \
  --stack-name webserver-stack \
  --template-body file://webserver.yaml
```

## CloudFormation Stack ansehen
```
aws cloudformation describe-stacks \
  --stack-name webserver-stack \
  --query 'Stacks[0].Outputs'
```

## CloudFormation Stack löschen
```bash
aws cloudformation delete-stack --stack-name webserver-stack
```

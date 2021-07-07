Importante mencionar que al configurar aws se tienen que seguir los pasos de este [video](https://www.youtube.com/watch?v=3_BF3XEk4RA)

# Instalación de AWS CLI
La documentación oficial para instalarlo está [aqui](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html)

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

# Configuración
La documentación oficial para configurar está [aqui](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

```bash
aws configure
```

más o menos, tienes que poner esta información (información de ejemplo por aws)

```bash
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

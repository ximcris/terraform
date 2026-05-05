# 🚀 AWS Infrastructure Script (VPC + EC2)

Este repositorio contiene un script en Bash que automatiza la creación de infraestructura básica en AWS utilizando la AWS CLI.

## 📌 ¿Qué hace este script?

El script realiza automáticamente los siguientes pasos:

1. **Crea una VPC**
   - CIDR: `192.168.0.0/24`
   - Nombre: `MyVpc`

2. **Habilita DNS en la VPC**
   - Activa `enable-dns-hostnames`

3. **Crea una Subred**
   - CIDR: `192.168.0.0/28`
   - Nombre: `subred1-cris`

4. **Configura la subred**
   - Habilita la asignación automática de IP pública

5. **Crea un Security Group**
   - Nombre: `gsmio`
   - Permite acceso SSH (puerto 22)

6. **Configura reglas de seguridad**
   - Permite conexiones entrantes por SSH desde `203.0.113.0/24`

7. **Lanza una instancia EC2**
   - AMI: `ami-0bdd88bd06d16ba03`
   - Tipo: `t3.micro`
   - Key Pair: `vockey`
   - Nombre: `miec2`

---

## ⚙️ Requisitos

Antes de ejecutar el script, asegúrate de tener:

- AWS CLI instalado → https://docs.aws.amazon.com/cli/
- Credenciales configuradas:
  ```bash
  aws configure
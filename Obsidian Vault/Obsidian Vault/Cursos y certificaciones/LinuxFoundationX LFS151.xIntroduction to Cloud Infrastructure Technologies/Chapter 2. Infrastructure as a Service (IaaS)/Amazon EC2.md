Las instancias de Amazon EC2 son, de hecho, Máquinas Virtuales.
***

1. Hipervisores: 
	En el corazón del servicio de Amazon EC2 se encuentran varios hipervisores de tipo 1, como Xen, KVM y [Nitro](https://aws.amazon.com/ec2/nitro/) (un hipervisor ligero basado en KVM más reciente que ofrece un rendimiento cercano al de un hardware físico).

Cuando se aprovisionan instancias de Amazon EC2, los usuarios pueden gestionar varios aspectos de la instancia, como el perfil de hardware, la imagen del sistema operativo con paquetes de software, almacenamiento adicional, la red conectada a la instancia y las reglas de firewall.

2. AMIs (Amazon Machine Images):
		
		Son plantillas preconfiguradas que contienen un sistema operativo y software adicionales.
		Se utilizan para lanzar instancias (servidores virtuales) en la nube de AWS.
		Pueden ser públicas (compartidas por otros usuarios) o privadas (creadas y gestionadas por ti).

3. Instance Types:

		Determinan las capacidades de CPU, memoria y almacenamiento de una instancia.
		Cada tipo está optimizado para un tipo específico de carga de trabajo.
		Se clasifican en familias según su propósito (por ejemplo, cómputo general, optimizado para memoria, optimizado para GPU, etc.).

4. Instance Types Importantes:

	  ==T2==: Equilibrados en la carga, ideales para aplicaciones con uso variable de CPU.
	
	  ==M5==: Equilibrio entre cómputo, memoria y almacenamiento, buenos para una amplia variedad de aplicaciones.
		
	  ==C5==: Optimizados para cómputo, excelente rendimiento para cargas de trabajo intensivas en CPU.
	
	  ==R5==: Optimizados para memoria, adecuados para bases de datos y aplicaciones de análisis de datos.
	
	  ==P3/P4==: Optimizados para GPU, ideales para cargas de trabajo de aprendizaje profundo y procesamiento de gráficos.
![[Pasted image 20231015023555.png|1000]]
### Aspects Configurables de Instancias EC2

- **Virtual Private Cloud (VPC):** Para aislar la red.
- **Grupos de Seguridad (Security Groups):** Para controlar el tráfico entrante/saliente de EC2 en redes de VPC.
- **Amazon Elastic Block Store (EBS):** Para la conexión de almacenamiento persistente.
- **Anfitriones Dedicados (Dedicated Hosts):** Para aprovisionar instancias en una máquina física reservada.
- **IP Elástica (Elastic IP):** Para remapear automáticamente una dirección IP estática.
- **CloudWatch:** Para monitorizar recursos y aplicaciones.
- **Auto Scaling:** Para redimensionar dinámicamente recursos.

<h2>Launch template </h2>
Un "launch template" en AWS es una plantilla que define cómo crear y configurar instancias (como servidores virtuales) de manera rápida y sencilla. Contiene información como el tipo de instancia, la imagen del sistema operativo, la configuración de red y otras opciones.

En lugar de configurar cada detalle cada vez que creas una instancia, puedes usar un "launch template" para establecer todas esas configuraciones de antemano. Esto te permite crear instancias de manera más eficiente y consistente.

Es especialmente útil cuando necesitas lanzar varias instancias con la misma configuración, ya que te ahorra tiempo y te asegura que todas las instancias se creen de la misma manera.

En resumen, un "launch template" es una herramienta que te permite definir y reutilizar la configuración de instancias en AWS para facilitar y agilizar el proceso de creación de servidores virtuales.

<h2>##Video demostrativo:##</h2>

![[43127e6e-9bee-44b3-b7ed-959d29fa2846-mp4_720p.mp4]]
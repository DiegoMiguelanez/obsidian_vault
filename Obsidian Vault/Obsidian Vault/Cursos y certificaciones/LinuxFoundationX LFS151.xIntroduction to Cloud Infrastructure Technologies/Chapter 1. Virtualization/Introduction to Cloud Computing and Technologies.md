Most of these service models fall into one of the following categories, as defined by NIST:

	Infrastructure as a Service (IaaS)
	Platform as a Service (PaaS)
	Software as a Service (SaaS).

In recent years, however, a variety of additional service models have been introduced to describe the needs and requirements of clients of remote computing services: 

	Analytics as a Service (AnaaS)
	API as a Service (AaaS)
	Big Data as a Service (BDaaS)
	Business Process as a Service (BPaaS)
	Code as a Service (CaaS)
	Communications Platform as a Service (CPaaS)
	Desktop as a Service (DaaS)
	Database as a Service (DBaaS)
	Function as a Service (FaaS)
	Monitoring as a Service (MaaS)
	Anything as a Service (XaaS).

# Cloud Deployment Models

Primarily, cloud is deployed under the following models: 

- **Private Cloud**  

		It is designated and operated solely for one organization. It can be hosted internally or externally and managed by internal teams or a third party. 
		
	[/*A private cloud can be built using a software stack like [OpenStack](https://www.openstack.org/).*/]
	 
		
- **Public Cloud**  

	    It is open to the public and anybody can use it, after swiping a credit card, of course. 
	    
[*/Amazon Web Services, Google Cloud Platform, and Microsoft Azure are examples of public clouds./*]

- **Hybrid Cloud  
    
	    **Public and private clouds can be bound together to offer a hybrid cloud. Such hybrid clouds are beneficial for:

1. Storage of sensitive information on the private cloud, while offering public services based on that information from a public cloud.
2. Meeting temporary resources needs during peak or times of high demand by scaling to the cloud, known as bursting, when such temporary needs of additional computing resources cannot be met by the private cloud.


![[Cloud_computing_types.svg|500]]
Para implementar modelos de implementación en la nube y las características de la computación en la nube, los proveedores de servicios en la nube y las herramientas de implementación de nube autoadministrada aprovechan software especializado para llevar a cabo la virtualización de hardware.

La virtualización implica crear versiones virtuales de componentes de hardware esenciales, permitiendo la creación de Máquinas Virtuales (VMs) que actúan como sistemas físicos aislados en un entorno virtual. Esto se logra mediante un software llamado hipervisor, que crea entornos operativos virtuales y aisla los recursos virtuales para su uso por los sistemas invitados.

***

Type-1 hypervisor (native or bare-metal) runs directly on top of a physical host machine's hardware, without the need for a host OS. Typically, they are found in enterprise settings. Examples of type-1 hypervisors:

	AWS Nitro
	IBM z/VM
	Microsoft Hyper-V 
	Nutanix AHV 
	Oracle VM Server for SPARC
	Oracle VM Server for x86
	Red Hat Virtualization
	VMware ESXi
	Xen.
	
Type-2 hypervisor (hosted) runs on top of the host's OS. Typically, they are for end-users, but they may be found in enterprise settings as well. Examples of type-2 hypervisors:

	Parallels Desktop for Mac
	VirtualBox
	VMware Player
	VMware Workstation.
	
And then there are the exceptions - hypervisors matching both categories, which can be listed redundantly under hypervisors of both type-1 and type-2. They are Linux kernel modules that act as both type-1 and type-2 hypervisors at the same time. Examples are:

	KVM
	bhyve.

Los hipervisores permiten la virtualización de componentes de hardware de computadora como la CPU, disco, red, RAM, etc., y permiten la instalación de máquinas virtuales invitadas sobre ellos. Esto posibilita la creación de múltiples máquinas virtuales con diferentes sistemas operativos en un solo hipervisor. La virtualización de hardware es respaldada por la mayoría de las CPU modernas y permite compartir los recursos de procesamiento del sistema anfitrión con múltiples sistemas invitados de manera segura y eficiente.

Además, muchas CPUs modernas también admiten la virtualización anidada, lo que permite la creación de VM dentro de otra VM. Aunque la virtualización es el método clave para convertir el hardware físico en un recurso de software virtualizado para la provisión de máquinas virtuales, también se pueden crear sistemas virtuales con la ayuda de emuladores. Esto permite que cualquier sistema operativo se ejecute en cualquier arquitectura o que programas se ejecuten en sistemas originalmente no admitidos. Los usuarios pueden aprovechar la flexibilidad de herramientas como QEMU y usarlas junto con un hipervisor como KVM para la provisión de VM.

A continuación, exploremos algunos métodos para crear VM con la ayuda de hipervisores.

***

  
La virtualización anidada, o "nested virtualization" en inglés, se refiere a la capacidad de ejecutar máquinas virtuales dentro de otras máquinas virtuales. Es decir, puedes crear un entorno de virtualización dentro de un entorno de virtualización ya existente.
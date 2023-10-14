  
KVM (Kernel-based Virtual Machine) es una solución de virtualización completa para Linux en hardware x86([[Arquitecturas]]).

Es un [[Modulo]] de virtualización cargable en el núcleo de Linux que convierte el núcleo en un hipervisor capaz de gestionar máquinas virtuales invitadas. 

Para que KVM funcione, se requieren extensiones de virtualización de hardware específicas, como Intel VT y AMD-V.

Diseñado originalmente para hardware x86, también ha sido adaptado a sistemas FreeBSD, S/390, PowerPC, IA-64 y ARM.



![[Kernel-based_Virtual_Machine.svg]]
KVM admite varios sistemas operativos invitados, como distribuciones de Linux, Windows, Solaris, etc.

KVM permite la abstracción de dispositivos como interfaces de red y discos, pero no del procesador.[KVM no proporciona una abstracción del procesador en el sentido de que no emula un procesador virtualizado. En su lugar, aprovecha las extensiones de virtualización de hardware proporcionadas por la CPU para permitir la ejecución de máquinas virtuales.

Las extensiones de virtualización de hardware, como Intel VT-x y AMD-V, permiten a la CPU ejecutar código de nivel de máquina (código de bajo nivel que se ejecuta directamente en la CPU) de manera segura y eficiente. Esto significa que las máquinas virtuales pueden ejecutar instrucciones del procesador directamente sin la necesidad de emular un procesador virtual.]

Expone la interfaz /dev/kvm que puede ser utilizada por un host de espacio de usuario externo para emulación. QEMU es un ejemplo de tal host.

KVM admite hosts anidados, lo que permite que las máquinas virtuales se ejecuten dentro de otras máquinas virtuales. También admite dispositivos enchufables en caliente como CPUs y dispositivos PCI. Es posible realizar un sobresubscripción para la asignación de recursos virtualizados adicionales que pueden no estar disponibles en el sistema. Para lograr la sobresubscripción en una VM, KVM intercambia dinámicamente recursos de otro invitado que no está utilizando el tipo de recurso necesario.
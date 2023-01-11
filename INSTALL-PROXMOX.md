![TechLabs](https://techlabs.net.br/wp-content/uploads/2021/09/logo_blog.png)

## :wrench: Instalação Home Assistant - Proxmox

1 - Faça o Download do Home Assistant OS na versão `.qcow2` [KVM/Proxmox](#https://www.home-assistant.io/installation/alternative)

Requisitos mínimos:
* 2GB RAM
* 32GB Disco
* 2vCPU

2 - Extraia o arquivo `.qcow2` presente no arquivo `.xz`, altere a extersão para `.img` e envie para o servidor Proxmox.

![img.png](assets/img.png)

3 - Crie uma VM com os seguintes parâmetros:

![img_1.png](assets/img_1.png)


* **OS:** Do not use any media.

![img_2.png](assets/img_2.png)


* **System:** Selecione a caixa Qemu Agent.

![img_3.png](assets/img_3.png)


* **Disk:** Clique na lixeira, para excluir o disco scsi0.

![img_4.png](assets/img_4.png)


* **CPU:** 1 Sockets / 2 Cores

![img_5.png](assets/img_5.png)


* **Memory:** 4096

![img_6.png](assets/img_6.png)


* **Network: Ajuste conforme a sua rede.**

![img_7.png](assets/img_7.png)


* **Confirm:** Start after created **(não marque essa opção)**

![img_8.png](assets/img_8.png)


4 - Abra o console do Proxmox e importe a img para a VM

* cd /var/lib/vz/template/iso

![img_9.png](assets/img_9.png)


* qm importdisk VMID /var/lib/vz/template/iso/haos_ova-9.4.img STORAGE_LOCATION

![img_10.png](assets/img_10.png)
![img_12.png](assets/img_12.png)


5 - Selecione a VM > Hardware

* Unused Disk 0 > ADD

![img_13.png](assets/img_13.png)


* ADD > EFI Disk: Selecione o disco da VM e desmarque Pre-Enroll Keys

![img_14.png](assets/img_14.png)


* Bios: OVMF (UEFI)

![img_15.png](assets/img_15.png)


6 - Selecione a VM > Options

* Boot Order: Mantém apenas a versão **scsi0**

![img_16.png](assets/img_16.png)

7 - Start VM

![img_17.png](assets/img_17.png)

---

## :sparkling_heart: Nos Ajude a Crescer
>Se este Material foi útil para você, ajude se inscrevendo no meu canal do YouTube.
>
>(https://youtube.com/techlabs94?sub_confirmation=1)
>
>Isso me incentiva a trazer mais materiais como este e muitos outros de redes e tecnologia.
>
>## ![YouTube Channel Subscribers](https://img.shields.io/youtube/channel/subscribers/UCWN6suTq5sZGqnSLos992Yw?style=social)

## :iphone: Contato e Informações
[![Whatsapp Badge](https://img.shields.io/badge/-Whatsapp-4CA143?style=flat-square&labelColor=4CA143&logo=whatsapp&logoColor=white&link=https://api.whatsapp.com/send?phone=5537999351046)](https://api.whatsapp.com/send?phone=5537999351046)

---
title: "Assistant Impl&#233;mentation d&#39;interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.interface.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Implémenter l'interface (Assistant C++)"
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Assistant Impl&#233;mentation d&#39;interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant implémente une interface pour un objet COM.  Les bibliothèques COM disponibles avec Visual Studio et Windows contiennent les implémentations de nombreuses interfaces.  Une implémentation d'interface est associée à un objet lorsqu'une instance de cet objet est créée. Elle assure les services que propose l'objet.  
  
 Pour plus d'informations sur les interfaces et les implémentations, consultez [Interfaces et implémentations d'interface](http://msdn.microsoft.com/library/windows/desktop/ms694356) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 **Implémenter l'interface à partir de**  
 Spécifie l'emplacement de la bibliothèque de types à partir de laquelle l'interface est créée.  
  
|Option|Description|  
|------------|-----------------|  
|**Projet**|La bibliothèque de types fait partie du projet.|  
|**Registre**|La bibliothèque de types est inscrite dans le système.  Les bibliothèques de types inscrites sont énumérées dans l'option **Bibliothèques de types disponibles**.|  
|**Fichier**|La bibliothèque de types n'est pas nécessairement inscrite dans le système, mais est contenue dans un fichier.  Vous devez indiquer l'emplacement du fichier dans l'option **Emplacement**.|  
  
 **Bibliothèques de types disponibles**  
 Affiche les bibliothèques de types disponibles contenant les définitions d'interfaces que vous pouvez implémenter.  Si vous cliquez sur **Fichier** sous **Implémenter une interface à partir du**, cette case à cocher n'est pas disponible pour la modification.  
  
 **Emplacement**  
 Affiche l'emplacement de la bibliothèque de types actuellement sélectionnée dans la liste **Bibliothèques de types disponibles**.  Si vous sélectionnez **Fichier** sous **Implémenter une interface à partir du**, cliquez sur le bouton de sélection pour rechercher un fichier contenant la bibliothèque de types à utiliser.  
  
 **Interfaces**  
 Affiche les interfaces dont les définitions sont indiquées dans la bibliothèque de types actuellement sélectionnée dans la zone **Bibliothèques de types disponibles**.  
  
> [!NOTE]
>  Les interfaces possédant le même nom que celles déjà implémentées par l'objet sélectionné ne s'affichent pas dans la zone **Interfaces**.  
  
|Bouton de transfert|Description|  
|-------------------------|-----------------|  
|**\>**|Ajoute à la liste **Implémenter les interfaces** le nom d'interface actuellement sélectionné dans la liste **Interfaces**.|  
|**\>\>**|Ajoute à la liste **Implémenter les interfaces** le nom de toutes les interfaces disponibles dans la liste **Interfaces**.|  
|**\<**|Supprime le nom d'interface actuellement sélectionné dans la liste **Implémenter les interfaces**.|  
|**\<\<**|Supprime les noms de toutes les interfaces actuellement affichées dans la liste **Implémenter les interfaces**.|  
  
 **Implémenter les interfaces**  
 Affiche le nom des interfaces que vous avez sélectionnées pour être implémentées sur votre objet.  
  
> [!NOTE]
>  Si vous ajoutez plusieurs interfaces dérivant de `IDispatch`, ou si vous tentez d'implémenter une interface dérivée d'une autre interface déjà présente dans votre classe, vous devez lever toute ambiguïté en ce qui concerne les entrées COM\_MAP.  Pour plus d'informations, consultez [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md).  
  
## Voir aussi  
 [Implémentation d'une interface](../ide/implementing-an-interface-visual-cpp.md)
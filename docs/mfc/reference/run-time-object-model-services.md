---
title: "Services du mod&#232;le objet au moment de l&#39;ex&#233;cution | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros des services du modèle objet au moment de l'exécution"
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Services du mod&#232;le objet au moment de l&#39;ex&#233;cution
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes [CObject](../../mfc/reference/cobject-class.md) et [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) encapsulent plusieurs services d'objet, notamment l'accès aux informations sur la classe à l'exécution, la sérialisation, et la création d'objets dynamiques.  Toutes les classes dérivées de `CObject` héritent de cette fonctionnalité.  
  
 L'accès aux informations sur la classe d'exécution vous permet de déterminer les informations sur une classe d'objets au moment de l'exécution.  La capacité de déterminer la classe d'un objet au moment de l'exécution est utile lorsque vous avez besoin de vérifications de type supplémentaires des arguments de la fonction et lorsque vous devez écrire un code spécial en fonction de la classe d'un objet.  Les informations sur la classe d'exécution ne sont pas prises en charge directement par le langage C\+\+.  
  
 La sérialisation est le processus d'écriture ou de lecture du contenu d'un objet vers et à partir d'un fichier.  Vous pouvez utiliser la sérialisation pour stocker le contenu d'un objet même après que l'application se termine.  L'objet peut ensuite être lu à partir du fichier lorsque l'application est redémarrée.  De tels objets de données sont dits "persistants".  
  
 La création d'objets dynamique permet de créer un objet d'une classe spécifiée au moment de l'exécution.  Par exemple, les objets document, vue, et cadre doivent prendre en charge la création dynamique car l'infrastructure doit les créer dynamiquement.  
  
 Le tableau suivant répertorie les macros MFC qui prennent en charge les données de la classe à l'exécution, la sérialisation, et la génération dynamique.  
  
 Pour plus d'informations sur ces services à l'exécution et la sérialisation, consultez l'article [Classe de CObject : Les informations sur l'accès à la classe en cours d'exécution](../../mfc/accessing-run-time-class-information.md).  
  
### Macros des services du modèle objet au moment de l'exécution  
  
|||  
|-|-|  
|[DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md)|Permet d'accéder aux informations sur la classe d'exécution \(doit être utilisé dans la déclaration de classe\).|  
|[DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)|Permet la création dynamique et l'accès aux informations sur la classe d'exécution \(doit être utilisé dans la déclaration de classe\).|  
|[DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md)|Permet la sérialisation dynamique et l'accès aux informations sur la classe d'exécution \(doit être utilisé dans la déclaration de classe\).|  
|[IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)|Permet d'accéder aux informations sur la classe d'exécution \(doit être utilisé dans l'implémentation de classe\).|  
|[IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)|Permet la création dynamique et l'accès aux informations sur la classe d'exécution \(doit être utilisé dans l'implémentation de classe\).|  
|[IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)|Permet la sérialisation et l'accès aux informations sur la classe d'exécution \(doit être utilisé dans l'implémentation de classe\).|  
|[RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)|Retourne la structure `CRuntimeClass` qui correspond à la classe nommée.|  
  
 OLE requiert souvent la création dynamique des objets au moment de l'exécution.  Par exemple, une application serveur OLE doit pouvoir créer des éléments OLE dynamiquement en réponse à une demande d'un client.  De même, un serveur Automation doit être en mesure de créer des éléments en réponse à des demandes des clients Automation.  
  
 La bibliothèque MFC fournit deux macros spécifiques à OLE.  
  
### Création dynamique des objets OLE  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE](../Topic/DECLARE_OLECREATE.md)|Active les objets à créer par l'intermédiaire de OLE Automation.|  
|[IMPLEMENT\_OLECREATE](../Topic/IMPLEMENT_OLECREATE.md)|Active les objets à créer par le système OLE.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
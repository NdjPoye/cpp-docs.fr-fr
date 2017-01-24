---
title: "Fabriques de classes et gestion des licences | Microsoft Docs"
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
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fabriques de classes, et licences"
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fabriques de classes et gestion des licences
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour créer une instance de votre commande utilisateur, une application conteneur appelle une fonction membre de la classe de fabrique du contrôle.  Étant donné que le contrôle est un objet OLE, la classe de fabrique est chargée de créer des instances de votre contrôle.  Chaque classe de contrôle OLE doit avoir une fabrique de la classe.  
  
 Une autre fonctionnalité importante de commandes OLE est la possibilité d'appliquer une licence.  ControlWizard vous permet d'incorporer des licences lors de la création de votre projet de commande.  Pour plus d'informations sur les licences des contrôles ActiveX que vous créez, consultez [Licences des contrôles ActiveX](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Le tableau suivant répertorie plusieurs macros et fonctions utilisées pour déclarer et implémenter la fabrique de la classe de votre contrôle et la licence du contrôle.  
  
### Fabriques de classes et gestion des licences  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE\_EX](../Topic/DECLARE_OLECREATE_EX.md)|Indique la fabrique de la classe pour une commande OLE ou une page de propriétés.|  
|[IMPLEMENT\_OLECREATE\_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|Implémente la fonction de la commande `GetClassID` et déclare une instance de la classe de fabrique.|  
|[BEGIN\_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|Démarre la déclaration de toutes les fonctions de licences.|  
|[END\_OLEFACTORY](../Topic/END_OLEFACTORY.md)|Termine la déclaration de toutes les fonctions de licences.|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|Vérifie si un contrôle est autorisé pour une utilisation sur un ordinateur particulier.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
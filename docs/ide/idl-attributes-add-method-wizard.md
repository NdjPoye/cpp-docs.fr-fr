---
title: "Attributs IDL, Assistant Ajout de m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.idlattrib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Ajout de méthode (C++)"
  - "Attributs IDL, Assistant Ajout de méthode"
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Attributs IDL, Assistant Ajout de m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Ajout de méthode pour spécifier les paramètres IDL \(Interface Definition Language\) de la méthode.  
  
 **id**  
 Définit l'ID numérique identifiant la méthode.  Consultez [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) dans le *Guide de référence MIDL*.  
  
 Cette zone n'est pas disponible pour les interfaces personnalisées et les dispinterfaces MFC.  
  
 **call\_as**  
 Spécifie le nom d'une méthode distante à laquelle cette méthode locale peut être mappée.  Consultez [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) dans le *Guide de référence MIDL*.  
  
 Fonctionnalité non disponible pour les dispinterfaces MFC.  
  
 **helpcontext**  
 Spécifie un ID de contexte permettant à l'utilisateur d'afficher des informations sur cette méthode dans le fichier d'aide.  Consultez [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) dans le *Guide de référence MIDL*.  
  
 Fonctionnalité non disponible pour les dispinterfaces MFC.  
  
 **helpstring**  
 Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.  Par défaut, elle a pour valeur « méthode *Nom de méthode* ». Consultez [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) dans le *Guide de référence MIDL*.  
  
 Fonctionnalité non disponible pour les dispinterfaces MFC.  
  
 **Attributs supplémentaires**  
 Fonctionnalité non disponible pour les dispinterfaces MFC.  
  
|Attribut|Description|  
|--------------|-----------------|  
|**hidden**|Indique que la méthode existe, mais ne doit pas être affichée dans un navigateur orienté utilisateur.  Consultez [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) dans le *Guide de référence MIDL*.|  
|**source**|Indique qu'un membre de la méthode est une source d'événements.  Consultez [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) dans le *Guide de référence MIDL*.|  
|`local`|Spécifie au compilateur MIDL que la méthode n'est pas distante.  Consultez [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) dans le *Guide de référence MIDL*.|  
|**restricted**|Spécifie que la méthode ne peut être appelée de façon arbitraire.  Consultez [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) dans le *Guide de référence MIDL*.|  
|**vararg**|Spécifie que la méthode accepte un nombre variable d'arguments.  Pour ce faire, le dernier argument doit être un tableau sécurisé de type **VARIANT** contenant tous les arguments restants.  Consultez [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) dans le *Guide de référence MIDL*.|  
  
## Voir aussi  
 [Ajout d'une méthode](../ide/adding-a-method-visual-cpp.md)   
 [Assistant Ajout de méthode](../ide/add-method-wizard.md)
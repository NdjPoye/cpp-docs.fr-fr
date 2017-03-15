---
title: "Attributs IDL, Assistant Ajout de propri&#233;t&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.idlattributes"
dev_langs: 
  - "C++"
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Attributs IDL, Assistant Ajout de propri&#233;t&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Ajout de propriété pour spécifier les paramètres IDL \(Interface Definition Language\) de la propriété.  
  
 **id**  
 Définit l'ID numérique identifiant la propriété.  Cette option n'est pas disponible pour les propriétés des interfaces personnalisées.  Consultez [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) dans le *Guide de référence MIDL*.  
  
 **helpcontext**  
 Spécifie un ID de contexte permettant à l'utilisateur d'afficher des informations sur cette propriété dans le fichier d'aide.  Consultez [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) dans le *Guide de référence MIDL*.  
  
 **helpstring**  
 Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.  Par défaut, elle a pour valeur « propriété *Nom de propriété* ». Consultez [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) dans le *Guide de référence MIDL*.  
  
## Autres options  
 Toutes les options ne sont pas disponibles pour tous les types de propriétés.  
  
|Option|Description|  
|------------|-----------------|  
|**bindable**|Indique que la propriété prend en charge la liaison des données.  Consultez [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738) dans le *Guide de référence MIDL*.  En ce qui concerne l'implémentation stock de la propriété, cette option est définie par défaut et n'est pas modifiable.|  
|**defaultbind**|Indique l'unique propriété qui peut être liée et qui représente au mieux l'objet.  Consultez [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) dans le *Guide de référence MIDL*.|  
|**displaybind**|Indique que cette propriété, aux yeux de l'utilisateur, doit apparaître comme pouvant être liée.  Consultez [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) dans le *Guide de référence MIDL*.|  
|**immediatebind**|Indique que la base de données est immédiatement avertie de toute modification apportée à une propriété d'un objet lié aux données.  Consultez [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) dans le *Guide de référence MIDL*.|  
|**defaultcollelem**|Indique que la propriété est une fonction accesseur pour un élément de la collection par défaut.  Consultez [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) dans le *Guide de référence MIDL*.|  
|**nonbrowsable**|Indique qu'un membre d'interface ou de dispinterface ne doit pas être affiché dans une fenêtre de propriétés.  Consultez [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) dans le *Guide de référence MIDL*.|  
|**requestedit**|Indique que la propriété prend en charge la notification **OnRequestEdit**. Consultez [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) dans le *Guide de référence MIDL*.  En ce qui concerne l'implémentation stock de la propriété, cette option est définie par défaut et n'est pas modifiable.|  
|**source**|Indique qu'un membre de la propriété est une source d'événements.  Consultez [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) dans le *Guide de référence MIDL*.|  
|**hidden**|Indique que la propriété existe, mais ne doit pas être affichée dans un navigateur orienté utilisateur.  Consultez [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) dans le *Guide de référence MIDL*.|  
|**restricted**|Spécifie que la propriété ne peut être appelée de façon arbitraire.  Consultez [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) dans le *Guide de référence MIDL*.|  
|`local`|Spécifie au compilateur MIDL que la propriété n'est pas distante.  Consultez [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) dans le *Guide de référence MIDL*.|  
  
## Voir aussi  
 [Ajout d'une propriété](../ide/adding-a-property-visual-cpp.md)   
 [Noms, Assistant Ajout de propriété](../ide/names-add-property-wizard.md)   
 [Implémentation d'une interface](../ide/implementing-an-interface-visual-cpp.md)   
 [Propriétés stock](../ide/stock-properties.md)
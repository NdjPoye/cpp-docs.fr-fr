---
title: "Assignation de l&#39;attribut noncreatable &#224; un objet ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, objets noncreatable"
  - "noncreatable (objets ATL)"
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assignation de l&#39;attribut noncreatable &#224; un objet ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez modifier les attributs d'un objet ATL COM afin qu'un client ne puisse pas directement créer l'objet.  Ainsi, l'objet est retourné par un appel de méthode sur un autre objet au lieu d'être directement créé.  
  
### Pour définir un objet comme noncreatable  
  
1.  Supprimez l'entrée [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) pour l'objet.  Si vous souhaitez définir l'objet comme noncreatable mais inscrire le contrôle, remplacez OBJECT\_ENTRY\_AUTO par [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md).  
  
2.  Ajoutez l'attribut [noncreatable](../../windows/noncreatable.md) à la coclasse du fichier .idl.  Par exemple :  
  
    ```  
    [  
       uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),  
       helpstring("MyObject"),  
      noncreatable  
    ]  
    coclass MyObject  
    {  
       [default] interface IMyInterface;  
    }  
    ```  
  
## Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)
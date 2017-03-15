---
title: "GetInterfaceClasses | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetInterfaceClasses"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceClasses (méthode)"
ms.assetid: 712c112f-b4ff-43c4-ad49-c4f4c13c48bd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetInterfaceClasses
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne l'objet `VCCodeClass` associé à une interface.  
  
## Syntaxe  
  
```  
  
      function GetInterfaceClasses(   
   strInterface,   
   oProject,   
   aryClasses    
);  
```  
  
#### Paramètres  
 *strInterface*  
 Nom de l'interface contenant les objets de classe.  
  
 *oProject*  
 Projet sélectionné.  
  
 *aryClasses*  
 \[out\] Tableau des objets de classe de l'interface.  
  
## Valeur de retour  
 L'objet <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeClass> associé à une interface.  
  
## Notes  
 Appelez cette fonction pour récupérer les classes associées à une interface.  
  
## Exemple  
  
```  
var aryClasses = new Array();  
GetInterfaceClasses(oInterface.Name, selProj, aryClasses);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetInterfaceType](../ide/getinterfacetype.md)
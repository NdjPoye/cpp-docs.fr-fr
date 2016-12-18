---
title: "GetInterfaceType | Microsoft Docs"
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
  - "GetInterfaceType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceType (méthode)"
ms.assetid: cc6403a8-0c2b-47f7-a8f7-9db95df87d5a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le type d'interface.  
  
## Syntaxe  
  
```  
  
      function GetInterfaceType(   
   oInterface    
);  
```  
  
#### Paramètres  
 *oInterface*  
 Objet <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface>.  
  
## Valeur de retour  
 Retourne la chaîne indiquant le type d'interface, tel que personnalisé, double, dispinterface ou oleautomation.  
  
## Notes  
 Appelez cette fonction pour obtenir le type d'interface.  
  
## Exemple  
 Consultez l'option [GetMaxID](../ide/getmaxid.md).  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetInterfaceClasses](../ide/getinterfaceclasses.md)
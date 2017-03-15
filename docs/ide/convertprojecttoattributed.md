---
title: "ConvertProjectToAttributed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ConvertProjectToAttributed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertProjectToAttributed (méthode)"
ms.assetid: 56a2d6e1-7e8e-4595-b2be-ade026593798
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ConvertProjectToAttributed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit un projet ATL sans attributs en projet avec attributs.  
  
## Syntaxe  
  
```  
  
function ConvertProjectToAttributed( );  
  
```  
  
## Valeur de retour  
 Retourne **true** si la conversion du projet a réussi ; sinon **false**.  
  
## Notes  
 Appelez cette fonction pour convertir un projet ATL d'un projet sans attributs en projet avec attributs.  Pour plus d'informations, consultez [Programmation par attributs](../windows/attributed-programming-concepts.md).  
  
## Exemple  
  
```  
// Create a function called CheckAddtoProject.  
function CheckAddtoProject(oProj)  
{  
// Is the project attributed already?  
   try  
   {  
      if (!IsAttributedProject(wizard))  
      {  
         // If the project is not converted to attributed, return false.  
         if (!ConvertProjectToAttributed(oProj))  
            return false;  
      }  
   }  
   catch (e)  
   {  
      var L_ErrMsg1_Text = "Error in CheckAddtoProject: ";  
      wizard.ReportError( L_ErrMsg1_Text + e.description);  
      return false;  
   }  
  
   return true;  
}  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [CanAddNonAttributed](../ide/canaddnonattributed.md)
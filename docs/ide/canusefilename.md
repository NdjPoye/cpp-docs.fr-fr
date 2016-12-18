---
title: "CanUseFileName | Microsoft Docs"
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
  - "CanUseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanUseFileName (méthode)"
ms.assetid: 60b669fa-9484-4435-b502-78ec8e960a00
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanUseFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifie si un fichier existe.  Si le fichier existe et qu'il n'est pas restreint, l'Assistant demande à l'utilisateur de fusionner le code à ajouter au fichier existant.  
  
## Syntaxe  
  
```  
  
      function CanUseFileName(   
   strFileName,   
   bCheckIfMidlHeader,   
   bCannotExist,   
   bSetMergeFlag    
);  
```  
  
#### Paramètres  
 `strFileName`  
 Nom du fichier à vérifier.  
  
 *bCheckIfMidlHeader*  
 Définissez la valeur **true** pour vérifier si le nom du fichier est généré par MIDL.  
  
 *bCannotExist*  
 Définissez la valeur **true** pour vérifier si le nom du fichier existe déjà et qu'il ne peut être remplacé.  
  
 *bSetMergeFlag*  
 Définissez la valeur **true** pour inclure le symbole MERG\_FILE indiquant que l'utilisateur peut fusionner le code au nom de fichier existant.  
  
## Valeur de retour  
 Retourne **true** si le paramètre `strFileName` est unique ou s'il est possible d'ajouter le code au fichier existant ; sinon **false**.  
  
## Notes  
 Appelez cette fonction pour vérifier si un nom de fichier existe.  Si le nom de fichier existe et qu'il n'est ni créé par MIDL, ni restreint, la fonction demande à l'utilisateur de fusionner le nouveau code au fichier existant.  
  
 Si le nom de fichier n'existe pas et n'est pas restreint, le fichier du nom spécifié est créé.  
  
 Si le nom de fichier est créé par MIDL ou est restreint, l'Assistant affiche un message d'erreur.  
  
## Exemple  
  
```  
case "HTML_FILE":  
if (!HTML_FILE.disabled)  
   {  
   if (!window.external.FindSymbol("HTML_FILE_VALID"))  
      {  
      bValid = CanUseFileName(obj.value, false, true);  
      if (!bValid)  
      break;  
      window.external.AddSymbol("HTML_FILE_VALID", true)  
      }  
   }  
   bValid = window.external.ValidateFile(HTML_FILE.value, vsCMValidateFileExtHtml);  
   break;   
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)
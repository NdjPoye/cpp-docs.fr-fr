---
title: "#line, directive (C/C++) | Microsoft Docs"
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
  - "#line"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#line (directive)"
  - "directive line (#line)"
  - "préprocesseur, directives"
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #line, directive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La directive `#line` indique au préprocesseur de modifier le numéro de ligne en interne enregistré et le nom de fichier du compilateur à un numéro de ligne et un nom de fichier donnés.  
  
## Syntaxe  
  
```  
  
#line   
digit-sequence ["filename"]  
```  
  
## Notes  
 Le compilateur utilise le numéro de ligne et le nom de fichier facultatif pour signaler les erreurs détectées pendant la compilation.  Le numéro de ligne fait généralement référence à la ligne d'entrée actuelle, et le nom de fichier fait référence au fichier d'entrée actuel.  Le numéro de ligne est incrémenté après que chaque ligne soit traitée.  
  
 La valeur *séquence de digit* peut être n'importe quel entier constant.  La macro de remplacement peut être effectuée sur les jetons de prétraitement, mais le résultat doit correspondre à la syntaxe correcte.  Le *nom de fichier* peut être toute combinaison de caractères et doit être placée entre guillemets \(**" "**\).  Si le *nom de fichier* est omis, le nom du fichier précédent reste inchangé.  
  
 Vous pouvez modifier le numero et le nom de ligne source en entrant une directive `#line`.  Le traducteur utilise le numéro de ligne et le nom de fichier pour déterminer les valeurs des macros prédéfinies **\_\_FILE\_\_** et **\_\_LINE\_\_**.  Vous pouvez utiliser ces macros pour insérer les messages d'erreur auto\-descriptifs dans le texte de programme.  Pour plus d'informations sur ces macros prédéfinies, consultez [Macros prédéfinies](../preprocessor/predefined-macros.md).  
  
 La macro **\_\_FILE\_\_** se développe vers une chaîne dont le contenu est le nom de fichier, entouré par des guillemets doubles \(**" "**\).  
  
 Si vous modifiez le numéro de ligne et le nom de fichier, le compilateur ignore les valeurs précédentes et continue de traiter avec les nouvelles valeurs.  La directive `#line` est généralement utilisée par les générateurs de programmes pour que les messages d'erreur fassent référence au fichier source d'origine et non au programme généré.  
  
 Les exemples suivants montrent `#line` et les macros **\_\_LINE\_\_** et **\_\_FILE\_\_**.  
  
 Dans cette instruction, le numéro de ligne en interne stocké est défini à 151 et le nom de fichier est remplacé par `copy.c`.  
  
```  
#line 151 "copy.c"  
```  
  
 Dans cet exemple, la macro `ASSERT` utilise les macros prédéfinies **\_\_LINE\_\_** et **\_\_FILE\_\_** pour imprimer un message d'erreur sur le fichier source si une « assertion » donnée n'est pas remplie.  
  
```  
#define ASSERT(cond)  
  
if( !(cond) )\  
{printf( "assertion error line %d, file(%s)\n", \  
__LINE__, __FILE__ );}  
```  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)
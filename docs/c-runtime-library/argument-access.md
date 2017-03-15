---
title: "Acc&#232;s &#224; un argument | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.arguments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros d'accès à un argument (C++)"
  - "listes d'arguments de longueur variable"
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Acc&#232;s &#224; un argument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les macros `va_arg`, `va_end`, et `va_start` permettent d'accéder aux arguments de la fonction lorsque le nombre d'arguments est variable.  Les macros sont définies dans STDARG.H pour la compatibilité ANSI C et dans VARARGS.H pour la compatibilité avec le système UNIX V.  
  
### macros d'accès à un argument  
  
|Macro|Utilisez|Équivalent de .NET Framework|  
|-----------|--------------|----------------------------------|  
|[va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Récupérer l'argument dans la liste|[\<caps:sentence id\="tgt9" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Classe de System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Réinitialiser le pointeur|[\<caps:sentence id\="tgt12" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Classe de System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Définissez le pointeur au début de la liste d'arguments|[\<caps:sentence id\="tgt15" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Classe de System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
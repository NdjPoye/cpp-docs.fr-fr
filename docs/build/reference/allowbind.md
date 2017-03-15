---
title: "/ALLOWBIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALLOWBIND (option Editbin)"
  - "/ALLOWBIND (option Editbin)"
  - "-ALLOWBIND (option Editbin)"
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie si une DLL peut être liée.  
  
```  
  
/ALLOWBIND[:NO]  
  
```  
  
## Notes  
 L'option de système **\/ALLOWBIND** définit un bit dans l'en\-tête d'une DLL pour indiquer à Bind.exe qu'il est possible de lier l'image.  La liaison peut permettre à une image de charger plus rapidement lorsque le chargeur ne doit pas se rebaser et effectuer les corrections d'adresse pour chaque DLL référencée.  Vous pouvez souhaiter ne pas lier une DLL si celle\-ci possède une signature numérique \(la liaison invalide la signature\).  La liaison est sans effet si la randomisation de l'espace d'adresse \(ASLR\) est activée pour l'image à l'aide de **\/DYNAMICBASE** sur les versions de Windows qui prennent en charge ASLR.  
  
 Utilisez **\/ALLOWBIND:NO** pour empêcher Bind.exe de lier le DLL.  
  
 Pour plus d'informations, consultez l'option de l'éditeur de liens [\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md).  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)
---
title: "/CLRHEADER | Microsoft Docs"
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
  - "/CLRHEADER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRHEADER (option Dumpbin)"
  - "CLRHEADER (option Dumpbin)"
  - "-CLRHEADER (option Dumpbin)"
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CLRHEADER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRHEADER file  
```  
  
## Notes  
 où :  
  
 `file`  
 Fichier image généré à l'aide de [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Notes  
 CLRHEADER affiche des informations sur les en\-têtes .NET utilisés dans un programme managé.  Le résultat indique l'emplacement et la taille \(en octets\) de l'en\-tête .NET et des sections de l'en\-tête.  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Si \/CLRHEADER est utilisé sur un fichier compilé avec \/clr, la sortie de dumpbin contiendra une section **clr Header:**.  La valeur de **flags** indique l'option \/clr qui a été utilisée :  
  
-   0  \-\- \/clr \(l'image peut contenir du code natif\).  
  
-   1  \-\- \/clr:safe \(l'image est en MSIL uniquement, capable de s'exécuter sur toute plateforme CLR et peut être vérifiable\).  
  
-   3  \-\- \/clr:pure \(l'image est en MSIL uniquement, mais ne peut s'exécuter que sur des plateformes x86\).  
  
 Vous pouvez également vérifier par programme si une image a été générée pour le Common Language Runtime.  Pour plus d'informations, consultez [Comment : déterminer si une image est native ou CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)
---
title: "_purecall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_purecall"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ntoskrnl.exe"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "purecall"
  - "_purecall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_purecall (fonction)"
  - "purecall (fonction)"
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _purecall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le Gestionnaire d’erreurs appel de fonction virtuelle pure par défaut. Le compilateur génère du code pour appeler cette fonction lorsqu’une fonction membre virtuelle pure est appelée.  
  
## Syntaxe  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## Notes  
 Le `_purecall` fonction est un détail d’implémentation du compilateur Microsoft Visual C\+\+ spécifiques à Microsoft. Cette fonction n’est pas destinée à être appelée directement par votre code, et ne qu’aucune déclaration d’en\-tête public. Il est documenté ici, car il s’agit d’une exportation publique de la bibliothèque Runtime C.  
  
 Un appel à une fonction virtuelle pure est une erreur, car il n’a aucune implémentation. Le compilateur génère du code pour appeler le `_purecall` fonction de gestionnaire d’erreurs lorsqu’une fonction virtuelle pure est appelée. Par défaut, `_purecall` termine le programme. Avant d’arrêter, le `_purecall` fonction appelle une `_purecall_handler` fonctionner s’il a été défini pour le processus. Vous pouvez installer votre propre fonction de gestionnaire d’erreurs pour les appels de fonction virtuelle pure, pour intercepter les fins de débogage ou de création de rapports. Pour utiliser votre propre gestionnaire d’erreurs, créez une fonction qui possède le `_purecall_handler` signature, puis utilisez [\_set\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) afin de faciliter le gestionnaire en cours.  
  
## Configuration requise  
 Le `_purecall` fonction n’a pas de déclaration d’un en\-tête. Le `_purecall_handler` typedef est défini dans \< stdlib.h \>.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_get\_purecall\_handler, \_set\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)
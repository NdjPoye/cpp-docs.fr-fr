---
title: "Erreur des outils &#201;diteur de liens LNK1309 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1309"
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

module type1 détecté ; non valide avec le commutateur \/CLRIMAGETYPE:type2  
  
 Un type d'image CLR a été demandé avec **\/CLRIMAGETYPE**, mais l'éditeur de liens n'a pas pu produire d'image de ce type, car un ou plusieurs modules étaient incompatibles avec celui\-ci.  
  
 Par exemple, l'erreur LNK1309 s'affiche si vous spécifiez **\/CLRIMAGETYPE:safe** et si vous passez un module généré avec **\/clr:pure**.  
  
 Elle s'affiche également si vous essayez de générer une application pure CLR d'un niveau de confiance partiel à l'aide de ptrustu\[d\].lib.  Pour plus d'information sur la création d'une application d'un niveau de confiance partiel, consultez [Comment : créer une application partiellement approuvée en supprimant la dépendance de la DLL de la bibliothèque CRT](../../dotnet/create-a-partially-trusted-application.md).  
  
 Pour plus d’informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) et [\/CLRIMAGETYPE \(Spécifier le type d'une image CLR\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).
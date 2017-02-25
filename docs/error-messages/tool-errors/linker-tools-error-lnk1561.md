---
title: "Erreur des outils &#201;diteur de liens LNK1561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1561"
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur des outils &#201;diteur de liens LNK1561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le point d'entrée doit être défini  
  
 L'éditeur de liens n'a pas trouvé de point d'entrée.  Il est possible que vous ayez tenté de créer un lien en tant que DLL, auquel cas vous devez utiliser l'option [\/DLL](../../build/reference/dll-build-a-dll.md).  Il se peut également que vous ayez oublié de spécifier le nom du point d'entrée ; créez alors le lien avec l'option [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 Sinon, vous devez inclure une fonction main, wmain, WinMain ou wMain dans votre code.  
  
 Si vous utilisez [LIB](../../build/reference/lib-reference.md) et souhaitez générer une .dll, cette erreur pourrait être due à la fourniture d'un fichier .def.  Dans ce cas, retirez le fichier .def de la génération.  
  
 L'exemple suivant génère l'erreur LNK1561 :  
  
```  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```
---
title: "Sp&#233;cification de DLL dont le chargement doit &#234;tre diff&#233;r&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD (option de l'éditeur de liens)"
  - "chargement différé de DLL"
  - "chargement différé de DLL, spécifier"
  - "DELAYLOAD (option de l'éditeur de liens)"
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sp&#233;cification de DLL dont le chargement doit &#234;tre diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez spécifier les DLL dont le chargement doit être différé avec l'option [\/delayload](../../build/reference/delayload-delay-load-import.md):`dllname` de l'éditeur de liens.  Si vous n'envisagez pas d'utiliser votre propre version d'une fonction d'assistance, vous devez également lier votre programme avec delayimp.lib \(applications de bureau\) ou dloadhelper.lib \(pour les applications du Windows store\).  
  
 Voici un exemple simple de chargement différé d'une DLL :  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 Générez la version DEBUG du projet.  Parcourez le code pas à pas à l'aide du débogueur : vous noterez que user32.dll est chargée seulement quand vous effectuez l'appel à `MessageBox`.  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)
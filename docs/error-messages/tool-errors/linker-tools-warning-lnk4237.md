---
title: "Avertissement des outils &#201;diteur de liens LNK4237 | Microsoft Docs"
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
  - "LNK4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4237"
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/SUBSYSTEM:NATIVE spécifié lors de l'importation à partir de 'dll' ; utilisez \/SUBSYSTEM:CONSOLE ou \/SUBSYSTEM:WINDOWS.  
  
 [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) a été spécifié lors de la génération d'une application Windows \(Win32\) qui utilise directement un ou plusieurs des éléments suivants :  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   une des dll msvcrt\*.  
  
 Pour résoudre cet avertissement, ne spécifiez pas **\/SUBSYSTEM:NATIVE**.
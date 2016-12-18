---
title: "Erreur de ligne de commande&#160;D8045 | Microsoft Docs"
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
  - "D8045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8045"
ms.assetid: 01c8808c-bac1-4b4d-8a90-b595f95e9318
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de ligne de commande&#160;D8045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de compiler le fichier C 'fichier' avec l'option \/clr  
  
 Seuls les fichiers de code source C\+\+ peuvent être passés à une compilation qui utilise **\/clr**.  Utilisez **\/TP** pour compiler un fichier .c en tant que fichier .cpp ; consultez [\/Tc, \/Tp, \/TC, \/TP \(Spécifier le type de fichier source\)](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) pour plus d'informations.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L'erreur D8045 peut également se produire si vous compilez une application ATL à l'aide de Visual C\+\+.  Pour plus d'informations, consultez [Comment : effectuer une migration vers \/clr](../../dotnet/how-to-migrate-to-clr.md).
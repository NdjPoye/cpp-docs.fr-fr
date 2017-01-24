---
title: "Avertissement des outils &#201;diteur de liens LNK4098 | Microsoft Docs"
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
  - "LNK4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4098"
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

conflit entre la bibliothèque par défaut 'bibliothèque' et les autres bibliothèques ; utilisez \/NODEFAULTLIB:library  
  
 Vous tentez une édition de liens avec des bibliothèques incompatibles.  
  
> [!NOTE]
>  Les bibliothèques runtime contiennent maintenant des directives pour empêcher le mélange de types différents.  Vous recevrez cet avertissement si vous tentez d'utiliser différents types de versions avec et sans débogage de la bibliothèque runtime dans le même programme.  Vous obtiendrez par exemple cet avertissement si vous avez compilé un fichier pour un type de bibliothèque runtime et un autre pour un autre type \(par exemple une bibliothèque à un seul thread et un multithread\) et avez ensuite tenté une édition de liens.  Vous devez compiler tous les fichiers sources pour qu'ils utilisent la même bibliothèque runtime.  Pour plus d'informations, consultez les options du compilateur [Utiliser la bibliothèque runtime](../../build/reference/md-mt-ld-use-run-time-library.md) \(**\/MD**, **\/MT**, **\/LD**\).  
  
 Vous pouvez utiliser le commutateur de l'éditeur de liens [\/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md) pour déterminer les bibliothèques dans lesquelles l'éditeur de liens recherche.  Si l'erreur LNK4098 s'affiche alors que vous souhaitez créer un fichier exécutable qui utilise par exemple les bibliothèques runtime à un seul thread sans débogage, utilisez l'option **\/VERBOSE:LIB** pour connaître les bibliothèques que l'éditeur de liens recherche.  L'éditeur de liens doit imprimer LIBC.lib et non LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib ou MSVCRTD.lib dans les bibliothèques recherchées.  Vous pouvez demander à l'éditeur de liens d'ignorer les bibliothèques runtime incorrectes par l'option [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) pour chaque bibliothèque que vous souhaitez ignorer.  
  
 Le tableau ci\-dessous indique les bibliothèques à ignorer selon la bibliothèque runtime que vous souhaitez utiliser.  
  
|Pour utiliser cette bibliothèque runtime|Ignorer ces bibliothèques|  
|----------------------------------------------|-------------------------------|  
|Un seul thread \(libc.lib\)|libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithread \(libcmt.lib\)|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithread utilisant des DLL \(msvcrt.lib\)|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Un seul thread débogage \(libcd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|Multithread débogage \(libcmtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|Multithread débogage utilisant des DLL \(msvcrtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 Si par exemple vous avez reçu cet avertissement alors que vous souhaitez créer un fichier exécutable utilisant la version un seul thread sans débogage des bibliothèques runtime, vous pouvez utiliser les options suivantes de l'éditeur de liens :  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```
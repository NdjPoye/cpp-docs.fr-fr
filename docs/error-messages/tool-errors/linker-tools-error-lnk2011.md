---
title: "Erreur des outils &#201;diteur de liens LNK2011 | Microsoft Docs"
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
  - "LNK2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2011"
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

objet précompilé absent de l'édition de liens ; l'image ne peut pas être exécutée  
  
 Si vous utilisez des en\-têtes précompilés, LINK requiert que tous les fichiers objets comportant des en\-têtes précompilés soient liés.  Si vous employez un fichier source pour générer un en\-tête précompilé destiné à être utilisé avec d'autres fichiers sources, vous devez maintenant inclure le fichier objet créé avec l'en\-tête précompilé.  
  
 Par exemple, si vous compilez un fichier appelé STUB.cpp pour créer un en\-tête précompilé à utiliser avec d'autres fichiers sources, vous devez effectuer l'édition de liens avec STUB.obj sous peine d'obtenir cette erreur.  Dans les lignes de commande ci\-dessous, la première ligne est utilisée pour créer un en\-tête précompilé, COMMON.pch, utilisé avec PROG1.cpp et PROG2.cpp dans les lignes deux et trois.  Le fichier STUB.cpp ne contient que des lignes `#include` \(les mêmes lignes `#include` que dans PROG1.cpp et PROG2.cpp\) et n'est utilisé que pour générer des en\-têtes précompilés.  Dans la dernière ligne, c'est STUB.obj qui doit être passé à l'éditeur de liens pour éviter LNK2011.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```
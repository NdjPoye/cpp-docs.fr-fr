---
title: "LNK2011 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9811bdb905df61bb77ea4af6bc4ced7c4ba42106
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2011"></a>Erreur des outils Éditeur de liens LNK2011
objet précompilé ne pas lié dans ; image ne peut pas s’exécuter  
  
 Si vous utilisez des en-têtes précompilés, LINK requiert que tous les fichiers objets créés avec des en-têtes précompilés soient liés. Si vous avez un fichier source que vous utilisez pour générer un en-tête précompilé à utiliser avec d’autres fichiers de code source, vous devez maintenant inclure le fichier objet créé avec l’en-tête précompilé.  
  
 Par exemple, si vous compilez un fichier appelé STUB.cpp pour créer un en-tête précompilé à utiliser avec d’autres fichiers de code source, vous devez lier avec stub.obj sous ou vous obtenez cette erreur. Dans les lignes de commande suivantes, la ligne est utilisé pour créer un en-tête précompilé, COMMON.pch, utilisé avec PROG1.cpp et PROG2.cpp dans les lignes deux et trois. Le fichier stub.cpp ne contient que `#include` lignes (le même `#include` lignes comme dans PROG1.cpp et PROG2.cpp) et est utilisée uniquement pour générer des en-têtes précompilés. Dans la dernière ligne stub.obj sous doivent être liées dans pour éviter LNK2011.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```
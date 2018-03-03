---
title: Erreur du compilateur C2480 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8b350c8f9098c56c503041614a4e68c780af5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2480"></a>Erreur du compilateur C2480
'identificateur' : 'thread' est uniquement valide pour les éléments de données d’étendue static  
  
 Vous ne pouvez pas utiliser le `thread` attribut avec une variable automatique, la donnée membre non statique, le paramètre de fonction ou sur des définitions ou déclarations de fonction.  
  
 Utilisez le `thread` attribut pour les variables globales, les données membres statiques et les variables statiques locales uniquement.  
  
 L’exemple suivant génère l’erreur C2480 :  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```
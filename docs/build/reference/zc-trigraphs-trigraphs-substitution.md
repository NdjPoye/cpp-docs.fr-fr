---
title: "-Zc : trigrammes (Substitution de trigrammes) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 739e772c87c937a552e07a32fa5bb80b1a1e2508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:, trigrammes (substitution de trigrammes) (C++)
Lorsque **/Zc : trigraphs** est spécifié, le compilateur remplace une séquence de caractères trigrammes à l’aide d’un caractère de ponctuation correspondant. Pour désactiver la substitution de trigrammes, spécifiez **/Zc:trigraphs-**. Par défaut, **/Zc : trigraphs** est désactivée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>Notes  
 Un trigraphe se compose de deux points d’interrogation consécutifs (??) suivis d’un troisième caractère unique. Par exemple, le compilateur remplace le « ?? = « trigraphe à l’aide du caractère « # ». Utilisez des trigraphes dans les fichiers sources C qui utilisent un jeu de caractères qui ne contient pas de représentation graphique pour certains caractères de ponctuation.  
  
 Pour une liste des trigrammes de C/C++ et un exemple qui montre comment utiliser les trigrammes, consultez [trigraphes](../../c-language/trigraphs.md).  
  
## <a name="see-also"></a>Voir aussi  
 [/Zc (conformité)](../../build/reference/zc-conformance.md)   
 [Trigraphes](../../c-language/trigraphs.md)
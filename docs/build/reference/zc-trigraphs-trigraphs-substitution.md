---
title: "-Zc : trigrammes (Substitution de trigrammes) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56068f6cb630ac12b9c8417940411616cec65c69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:, trigrammes (substitution de trigrammes) (C++)
Lorsque **/Zc : trigraphs** est spécifié, le compilateur remplace une séquence de caractères trigrammes à l’aide d’un caractère de ponctuation correspondant. Pour désactiver la substitution de trigrammes, spécifiez **/Zc:trigraphs-**. Par défaut, **/Zc : trigraphs** est désactivée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>Remarques  
 Un trigraphe se compose de deux points d’interrogation consécutifs (??) suivis d’un troisième caractère unique. Par exemple, le compilateur remplace le « ?? = « trigraphe à l’aide du caractère « # ». Utilisez des trigraphes dans les fichiers sources C qui utilisent un jeu de caractères qui ne contient pas de représentation graphique pour certains caractères de ponctuation.  
  
 Pour une liste des trigrammes de C/C++ et un exemple qui montre comment utiliser les trigrammes, consultez [trigraphes](../../c-language/trigraphs.md).  
  
## <a name="see-also"></a>Voir aussi  
 [/Zc (conformité)](../../build/reference/zc-conformance.md)   
 [Trigraphes](../../c-language/trigraphs.md)
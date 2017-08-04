---
title: "Constantes d’action signal | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f316218673d83187f29934ebd75a838b31005912
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="signal-action-constants"></a>signal, constantes action
L’action effectuée lors de la réception du signal d’interruption varie selon la valeur de `func`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Remarques  
 L’argument `func` doit être une adresse de fonction ou une des constantes manifestes répertoriées ci-dessous et définies dans SIGNAL.H.  
  
 `SIG_DFL`  
 Utilise la réponse par défaut du système. Si le programme appelant utilise des E/S de flux, les mémoires tampon créées par la bibliothèque Runtime ne sont pas vidées.  
  
 `SIG_IGN`  
 Ignore le signal d’interruption. Cette valeur ne doit jamais être donnée pour `SIGFPE`, car l’état à virgule flottante du processus reste non défini.  
  
 `SIG_SGE`  
 Indique qu’une erreur s’est produite dans le signal.  
  
 `SIG_ACK`  
 Indique qu’un accusé de réception a été reçu.  
  
 `SIG_ERR`  
 Un type de retour d’un signal indiquant une erreur s’est produite.  
  
## <a name="see-also"></a>Voir aussi  
 [signal](../c-runtime-library/reference/signal.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)

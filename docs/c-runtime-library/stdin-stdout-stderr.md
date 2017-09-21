---
title: stdin, stdout, stderr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
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
ms.openlocfilehash: 331b60a8cd06e42c032c6d8c81b58b8e4f4501ae
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr
## <a name="syntax"></a>Syntaxe  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Remarques  
 Il s’agit des flux standard pour l’entrée, la sortie et la sortie d’erreur.  
  
 Par défaut, une entrée standard est en lecture à partir du clavier, tandis que la sortie standard et l’erreur standard sont affichées à l’écran.  
  
 Les pointeurs de flux suivants sont disponibles pour accéder aux flux standard :  
  
|Pointeur|Flux|  
|-------------|------------|  
|`stdin`|Entrée standard|  
|**stdout**|Objet de flux de sortie standard|  
|`stderr`|Erreur standard|  
  
 Ces pointeurs peuvent être utilisés comme arguments pour fonctions. Certaines fonctions, telles que **getchar** et `putchar`, utilisent `stdin` et **stdout** automatiquement.  
  
 Ces pointeurs sont des constantes et il n’est pas possible de leur affecter de nouvelles valeurs. La fonction `freopen` peut être utilisée pour rediriger les flux vers des fichiers sur disque ou d’autres appareils. Le système d’exploitation vous permet de rediriger l’entrée et la sortie standard d’un programme au niveau de la commande.  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../c-runtime-library/stream-i-o.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
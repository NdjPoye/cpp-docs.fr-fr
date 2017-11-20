---
title: Constantes setvbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs: C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 16a5a215657a6d447c43c7ba327ef0d5f31d4abb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setvbuf-constants"></a>setvbuf, constantes
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 Ces constantes représentent le type de mémoire tampon pour `setvbuf`.  
  
 Les valeurs possibles sont données par les constantes manifestes suivantes :  
  
|Constante|Signification|  
|--------------|-------------|  
|`_IOFBF`|Mise en mémoire tampon complète : la mémoire tampon spécifiée dans l’appel à `setvbuf` est utilisée et sa taille est spécifiée dans l’appel `setvbuf`. Si le pointeur de la mémoire tampon est **NULL**, une mémoire tampon de la taille spécifiée automatiquement allouée est utilisée.|  
|`_IOLBF`|Comme pour `_IOFBF`.|  
|`_IONBF`|Aucune mémoire tampon n’est utilisée, quels que soient les arguments dans l’appel à `setvbuf`.|  
  
## <a name="see-also"></a>Voir aussi  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
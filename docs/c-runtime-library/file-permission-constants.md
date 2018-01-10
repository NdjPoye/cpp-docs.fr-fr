---
title: "Constantes d’autorisations de fichier | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs: C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 123b5f14c6d13e7ee7ff41de00816234d6e45fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="file-permission-constants"></a>Constantes d'autorisations de fichier
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>Notes  
 Une de ces constantes est obligatoire quand `_O_CREAT` (`_open`, `_sopen`) est spécifié.  
  
 L’argument `pmode` spécifie les paramètres d’autorisation du fichier comme suit.  
  
|Constante|Signification|  
|--------------|-------------|  
|`_S_IREAD`|Lecture autorisée|  
|`_S_IWRITE`|Écriture autorisée|  
|`_S_IREAD` &#124; `_S_IWRITE`|Lecture et écriture autorisées|  
  
 Lorsqu’elle est utilisée en tant qu’argument `pmode` pour `_umask`, la constante manifeste définit le paramètre d’autorisation, comme suit.  
  
|Constante|Signification|  
|--------------|-------------|  
|`_S_IREAD`|Écriture non autorisée (le fichier est en lecture seule)|  
|`_S_IWRITE`|Lecture non autorisée (le fichier est en écriture seule)|  
|`_S_IREAD` &#124; `_S_IWRITE`|Pas d’autorisation en lecture ou écriture|  
  
## <a name="see-also"></a>Voir aussi  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [Types standard](../c-runtime-library/standard-types.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
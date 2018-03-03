---
title: Mappages de constantes et de variables globales | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb767bb3dbfbde8d73ab81acc444a772a05e7880
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="constant-and-global-variable-mappings"></a>Mappage de constantes et de variables globales
Ces mappages de constantes de texte générique, de variables globales et de type standard sont définis dans TCHAR.H et varient selon que la constante `_UNICODE` ou `_MBCS` a été définie dans votre programme.  
  
### <a name="generic-text-constant-and-global-variable-mappings"></a>Mappages de constantes de texte générique et de variables globales  
  
|Texte générique - nom de l’objet|SBCS (_UNICODE, _MBCS non définis)|_MBCS défini|_UNICODE défini|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="see-also"></a>Voir aussi  
 [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md)   
 [Mappages de types de données](../c-runtime-library/data-type-mappings.md)   
 [Mappages de routine](../c-runtime-library/routine-mappings.md)   
 [Exemple de programme de texte générique](../c-runtime-library/a-sample-generic-text-program.md)   
 [Utilisation de mappages de texte générique](../c-runtime-library/using-generic-text-mappings.md)
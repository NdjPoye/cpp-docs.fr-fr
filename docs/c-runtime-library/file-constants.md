---
title: Constantes de fichier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs:
- C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59e108f8674b002cdbc5e7ab0b9c1868eea632df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="file-constants"></a>Constantes de fichier
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>Notes  
 L’expression d’entier formée à partir d’une ou plusieurs de ces constantes détermine le type des opérations de lecture ou écriture autorisées. Elle est formée en combinant une ou plusieurs constantes avec une constante de mode de traduction.  
  
 Les constantes de fichier sont les suivantes :  
  
 `_O_APPEND`  
 Repositionne le pointeur de fichier à la fin du fichier avant chaque opération d'écriture.  
  
 `_O_CREAT`  
 Crée et ouvre un nouveau fichier pour l’écriture ; cela n’a aucun effet si le fichier spécifié par *filename* existe.  
  
 `_O_EXCL`  
 Retourne une valeur d'erreur si le fichier spécifié par *filename* existe. S’applique uniquement lors de l’utilisation avec `_O_CREAT`.  
  
 `_O_RDONLY`  
 Ouvre un fichier en lecture seule ; si cet indicateur est spécifié, ni `_O_RDWR` ni `_O_WRONLY` ne peut être donné.  
  
 `_O_RDWR`  
 Ouvre le fichier pour la lecture et l’écriture ; si cet indicateur est spécifié, ni `_O_RDONLY` ni `_O_WRONLY` ne peut être donné.  
  
 `_O_TRUNC`  
 Ouvre un fichier existant et le tronque à une longueur nulle. Le fichier doit disposer d'une autorisation en écriture. Le contenu du fichier est détruit. Si cet indicateur est spécifié, vous ne pouvez pas spécifier `_O_RDONLY`.  
  
 `_O_WRONLY`  
 Ouvre un fichier en écriture seule ; si cet indicateur est spécifié, ni `_O_RDONLY` ni `_O_RDWR` ne peut être donné.  
  
## <a name="see-also"></a>Voir aussi  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
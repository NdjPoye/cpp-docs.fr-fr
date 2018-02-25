---
title: '&lt;ccomplex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb279929a460c43bb7ca564615fde494e3a0eb99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;
Inclut l’en-tête [\<complex>](../standard-library/complex.md) de la bibliothèque C++ Standard, qui inclut l’en-tête \<complex.h> de la bibliothèque C Standard et ajoute les noms associés à l’espace de noms `std`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#include <ccomplex>  
  
```  
  
## <a name="remarks"></a>Notes  
 L'inclusion de cet en-tête garantit également que les noms déclarés à l'aide d'une liaison externe dans l'en-tête de la bibliothèque C standard soient déclarés dans l'espace de noms `std`.  
  
 Le nom `clog`, qui est déclaré dans \<complex.h>, n’est pas défini dans l’espace de noms `std` en raison de conflits potentiels avec le nom `clog` qui est déclaré dans [\<iostream>](../standard-library/iostream.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Vue d’ensemble de la bibliothèque C++ Standard](../standard-library/cpp-standard-library-overview.md)




---
title: _local_unwind2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs:
- C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b0c027623f5b562219e46c67ef730754538d602
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="localunwind2"></a>_local_unwind2
Fonction CRT interne. Exécute tous les gestionnaires de terminaisons répertoriés dans la table d'étendue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _local_unwind2(  
   PEXCEPTION_REGISTRATION xr,  
   int stop  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `xr`  
 Enregistrement d'inscription associé à une table d'étendue.  
  
 [in] `stop`  
 Niveau lexical qui indique là où `_local_unwind2` doit s'arrêter.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est employé uniquement par l'environnement d'exécution. N'appelez pas la méthode dans votre code.  
  
 Quand cette méthode exécute des gestionnaires de terminaisons, elle part du niveau lexical actuel et parcourt les autres situés au-dessus jusqu'à atteindre celui indiqué par `stop`. Elle n'exécute pas les gestionnaires de terminaisons au niveau indiqué par `stop`.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
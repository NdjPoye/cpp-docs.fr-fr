---
title: bad_function_call, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: functional/std::bad_function_call
dev_langs: C++
helpviewer_keywords: bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5268bce61a848b59dbfd43af12b16bae35f9f202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="badfunctioncall-class"></a>bad_function_call, classe
Signale un appel de fonction incorrect.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_function_call  
 : public std::exception {  
 };  
```  
  
## <a name="remarks"></a>Notes  
 La classe décrit une exception levée pour indiquer qu’un appel à `operator()` sur une [classe function](../standard-library/function-class.md) est incorrect

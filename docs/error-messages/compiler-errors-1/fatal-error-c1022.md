---
title: "Erreur irrécupérable C1022 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1022
dev_langs: C++
helpviewer_keywords: C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dfa41aad6cb03840d0fa4c6a6ee9622d5f5c57e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1022"></a>Erreur irrécupérable C1022
#endif attendu  
  
 Une directive `#if`, `#ifdef`ou `#ifndef` n’a aucune directive `#endif` correspondante. Vérifiez que chaque directive `#if`, `#ifdef`ou `#ifndef` a une directive `#endif`correspondante.  
  
 L’exemple suivant génère l’erreur C1022 :  
  
```  
// C1022.cpp  
#define true 1  
  
#if (true)  
#else   
#else    // C1022  
```  
  
 Solution possible :  
  
```  
// C1022b.cpp  
// compile with: /c  
#define true 1  
  
#if (true)  
#else   
#endif  
```
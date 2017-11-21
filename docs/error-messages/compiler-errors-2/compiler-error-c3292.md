---
title: Erreur du compilateur C3292 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3292
dev_langs: C++
helpviewer_keywords: C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5bad02a4c7eae9a30855596ccb1695430c4f15e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3292"></a>Erreur du compilateur C3292
impossible de rouvrir l'espace de noms cli  
  
 L’espace de noms cli ne peut pas être déclaré dans votre code.  Pour plus d’informations, consultez [plateforme, par défaut et espaces de noms cli](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3292.  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```
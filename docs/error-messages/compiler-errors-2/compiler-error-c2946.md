---
title: Erreur du compilateur C2946 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2946
dev_langs: C++
helpviewer_keywords: C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5e02ea2e96a3c6356a9372700c80d000aa48992
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2946"></a>Erreur du compilateur C2946
instanciation explicite ; 'class' n’est pas une spécialisation de classe de modèle  
  
 Vous ne pouvez pas instancier explicitement une classe non basée sur des modèles.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2946.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```
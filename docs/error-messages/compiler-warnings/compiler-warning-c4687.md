---
title: Avertissement du compilateur C4687 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41992e91b40fc17ef73ccb75828796b31ee3249e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4687"></a>Avertissement du compilateur C4687
'classe' : une classe abstraite sealed ne peut pas implémenter une interface 'interface'  
  
 Un type abstrait sealed n’est généralement utile pour contenir les fonctions membres statiques.  
  
 Pour plus d’informations, consultez [abstraite](../../windows/abstract-cpp-component-extensions.md)et [sealed](../../windows/sealed-cpp-component-extensions.md).  
  
 Par défaut, C4687 est émis en tant qu’erreur. Vous pouvez supprimer l’erreur C4687 avec le [avertissement](../../preprocessor/warning.md) pragma. Si vous êtes certain que vous souhaitez implémenter une interface dans un type abstrait sealed, vous pouvez supprimer l’erreur C4687.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4687.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```
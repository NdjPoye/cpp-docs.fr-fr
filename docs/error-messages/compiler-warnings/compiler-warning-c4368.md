---
title: Avertissement du compilateur C4368 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4368
dev_langs: C++
helpviewer_keywords: C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9694eb05a2d14ff8dac49c0e9a3cb29dcf52bbac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4368"></a>Avertissement du compilateur C4368
Impossible de définir 'membre' en tant que membre de 'type' managé : les types mixtes ne sont pas pris en charge.  
  
 Vous ne pouvez pas incorporer un membre de données native dans un type CLR.  
  
 Toutefois, vous pouvez déclarer un pointeur vers un type natif et contrôler sa durée de vie dans le constructeur et le destructeur et le finaliseur de votre classe managée. Pour plus d’informations, consultez [destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Cet avertissement est toujours émis en tant qu’erreur. Utilisez le [avertissement](../../preprocessor/warning.md) pragma pour désactiver l’erreur C4368.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4368.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```
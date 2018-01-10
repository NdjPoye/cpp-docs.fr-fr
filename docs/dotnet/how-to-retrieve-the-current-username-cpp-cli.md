---
title: "Comment : récupérer le nom d’utilisateur en cours (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1532647327c039994a1d09ee8b7eacc2c341f88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-retrieve-the-current-username-ccli"></a>Comment : récupérer le nom d'utilisateur actuel (C++/CLI)
L’exemple de code suivant illustre la récupération du nom d’utilisateur en cours (le nom de l’utilisateur connecté à Windows). Le nom est stocké dans le <xref:System.Environment.UserName%2A> chaîne, qui est défini dans le <xref:System.Environment> espace de noms.  
  
## <a name="example"></a>Exemple  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérations Windows (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
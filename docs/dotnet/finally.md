---
title: Enfin | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd357c8eeed9eddc6940ce02de6e5d2b4f8c68d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="finally"></a>finally
En plus de `try` et `catch` prend en charge des exceptions CLR, dans un `finally` clause. La sémantique est identique à la `__finally` bloquer dans les exceptions structurées (SEH). A `__finally` bloc peut suivre un `try` ou `catch` bloc.  
  
## <a name="remarks"></a>Notes  
 L’objectif de la `finally` bloc consiste à nettoyer les ressources qui restent après l’exception s’est produite. Notez que le `finally` bloc est toujours exécuté, même si aucune exception n’est levée. Le `catch` bloc est exécuté uniquement si une exception managée est levée dans associé `try` bloc.  
  
 `finally`est un mot clé contextuel ; consultez [mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre un simple `finally` bloc :  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
```Output  
in catch  
MyException  
in finally  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions](../windows/exception-handling-cpp-component-extensions.md)
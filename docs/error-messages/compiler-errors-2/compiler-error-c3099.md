---
title: Erreur du compilateur C3099 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a644a27c834efcd3c3857241927a6e618f600d0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3099"></a>Erreur du compilateur C3099
'mot clé' : utilisez [System::AttributeUsageAttribute] pour les attributs managés ; utilisez [Windows::Foundation::Metadata::AttributeUsageAttribute] pour les attributs WinRT  
  
 Utilisez <xref:System.AttributeUsageAttribute> pour déclarer **/CLR** attributs. Utilisez `Windows::Foundation::Metadata::AttributeUsageAttribute` pour déclarer des attributs Windows Runtime.  
  
 Pour plus d’informations sur les attributs/CLR, consultez [les attributs définis par l’utilisateur](../../windows/user-defined-attributes-cpp-component-extensions.md). Pour obtenir des attributs pris en charge dans Windows Runtime, consultez [Windows.Foundation.Metadata espace de noms](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'erreur C3099 et montre comment la corriger.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```
---
title: Domaines d’application et Visual C++ | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ddb60b3fad6c230677e2098dd89a723198bea8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="application-domains-and-visual-c"></a>Domaines d'application et Visual C++
Si vous avez un `__clrcall` une fonction virtuelle, la vtable sera par domaine d’application (appdomain). Si vous créez un objet dans un domaine d’application, vous pouvez uniquement appeler la fonction virtuelle à partir de cet AppDomain. En mode mixte (**/CLR**) aura vtables par processus si votre type n’a pas `__clrcall` fonctions virtuelles. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 Pour plus d'informations, consultez  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)
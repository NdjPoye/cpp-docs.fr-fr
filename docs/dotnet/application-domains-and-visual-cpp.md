---
title: "Domaines d’application et Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a66731b9645458441f1c3e1f211c74be698e7231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="application-domains-and-visual-c"></a>Domaines d'application et Visual C++
Si vous avez un `__clrcall` une fonction virtuelle, la vtable sera par domaine d’application (appdomain). Si vous créez un objet dans un domaine d’application, vous pouvez uniquement appeler la fonction virtuelle à partir de cet AppDomain. Toutes les fonctions définies dans **/CLR : pure** compilands utiliser le `__clrcall` convention d’appel. Par conséquent, toutes les vtables définies dans **/CLR : pure** compilands sont par appdomain. En mode mixte (**/CLR**) aura vtables par processus si votre type n’a pas `__clrcall` fonctions virtuelles. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 Pour plus d'informations, consultez  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [Comment : migrer vers/clr : pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)
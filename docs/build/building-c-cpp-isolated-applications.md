---
title: "Génération C/C++ d’Applications isolées | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76b0c1fa5b509ae495a12fb63164d7da01f402aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications"></a>Génération d'applications isolées C/C++
Une application isolée dépend uniquement les assemblys côte à côte et le lie à ses dépendances à l’aide d’un manifeste. Il n’est pas requis pour votre application soit complètement isolée pour pouvoir s’exécuter correctement sur Windows ; Toutefois, en faisant l’acquisition d’établissement d’isoler totalement votre application, vous pouvez gagner du temps si vous avez besoin votre application à l’avenir de service. Pour plus d’informations sur les avantages de fabrication isoler totalement votre application, consultez [Applications isolées](http://msdn.microsoft.com/library/aa375190).  
  
 Lorsque vous générez votre application C/C++ native à l’aide de Visual C++, Visual Studio par défaut, système de projet génère un fichier manifeste qui décrit les dépendances de votre application sur les bibliothèques Visual C++. S’il s’agit des seules dépendances votre application a, il devient alors une application isolée dès qu’elle est régénérée avec Visual Studio. Si votre application utilise d’autres bibliothèques lors de l’exécution, vous devrez peut-être régénérer ces bibliothèques en tant qu’assemblys côte à côte en suivant les étapes décrites dans [création d’assemblys C/C++ côte-à-côte](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts d’Applications isolées et les assemblys côte à côte](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Génération d’applications isolées et d’assemblys côte à côte C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
---
title: Les applications Windows universelles (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9ad7a56663081941f3b3ca18193da55d5df2ab6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="universal-windows-apps-c"></a>Applications de plateforme Windows universelle (C++)
Les applications universelles Windows Platform (UWP) sont basées sur un ensemble de principes de conception qui mettent l’accent sur les interfaces utilisateur simples centrées sur le contenu s’ajuste automatiquement pour différentes tailles d’écran sur différents appareils. Vous créez l'interface utilisateur dans le balisage XAML et le code-behind en C++ natif. Vous pouvez également créer des composants (DLL) qui peuvent être utilisés par des applications de plateforme Windows universelle qui sont écrites dans d'autres langages. La surface de l’API pour les applications UWP est le Windows Runtime, qui est une bibliothèque bien factorisée fournissant une grande variété de services de système d’exploitation.  

> [!TIP]  
> Pour Windows 10, vous pouvez utiliser le convertisseur d’application de bureau pour empaqueter votre application de bureau existante pour le déploiement via le Windows Store. Pour plus d’informations, consultez [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) et [Déplacer votre application de bureau vers la plateforme universelle Windows (UWP) avec le pont du bureau](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).
  
  
## <a name="uwp-apps-that-use-ccx"></a>Applications de plateforme Windows universelle utilisant C++/CX  
  
|||  
|-|-|  
|[Informations de référence du langage Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Décrit l’ensemble des extensions qui simplifient la consommation par C++ des APIs Windows Runtime et activer la gestion des erreurs sont basée sur les exceptions.|  
|[Génération d’applications et de bibliothèques (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Décrit comment créer des DLL et des bibliothèques statiques qui sont accessibles à partir d’une application ou d’un composant C++/CX.|  
|[Didacticiel : Créer votre première application du Windows Store en C++](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Une procédure pas à pas qui présente les concepts de base du développement d’applications de plateforme Windows universelle en C++. (Pas encore mise à jour pour le développement d’applications de plateforme Windows universelle sur Windows 10.)|  
|[Création de composants Windows Runtime en C++](https://docs.microsoft.com/en-us/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Décrit comment créer des DLL que d’autres composants et applications de plateforme Windows universelle peuvent consommer.|  
|[Développement de jeux](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|Décrit comment utiliser DirectX et C++ pour créer des jeux.|  
  
## <a name="universal-windows-platform-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Applications de la plateforme Windows universelle qui utilisent la bibliothèque Windows Runtime modèle C++ (WRL) 
 La bibliothèque de modèles Windows Runtime C++ fournit les interfaces COM de bas niveau qui code C++ ISO peut accéder au Windows Runtime dans un environnement sans exception. Dans la plupart des cas, nous vous recommandons d’utiliser C + c++ / CX au lieu de la bibliothèque de modèles Windows Runtime C++ pour le développement d’applications de plateforme Windows universelle. Pour plus d’informations sur la bibliothèque de modèles Windows Runtime C++, consultez [bibliothèque de modèles Windows Runtime C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Visual C++](../visual-cpp-in-visual-studio.md)


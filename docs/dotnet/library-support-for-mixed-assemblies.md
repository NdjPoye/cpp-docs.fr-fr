---
title: Prise en charge pour les assemblys mixtes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6f999a75a8f818fccabada840a2a6e9fc70447cb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="library-support-for-mixed-assemblies"></a>Prise en charge de bibliothèque pour les assemblys mixtes
Visual C++ prend en charge l’utilisation de la bibliothèque C++ Standard, la bibliothèque CRT, ATL et MFC pour les applications compilées avec [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md). Ainsi, les applications existantes qui utilisent ces bibliothèques à utiliser aussi bien les fonctionnalités de .NET Framework.  
  
 Cette prise en charge introduit les bibliothèques DLL et d’importation nouveau suivantes :  
  
-   Msvcmrt [d] .lib si vous compilez avec/CLR. Assemblys mixtes est lié à cette bibliothèque d’importation.  
  
 Cette prise en charge offre que plusieurs avantages connexes :  
  
-   Le CRT et la bibliothèque C++ Standard sont disponibles pour le code mixte et pure. Le CRT et la bibliothèque C++ Standard fournis ne sont pas vérifiables ; Finalement, vos appels sont encore routés aux mêmes CRT et bibliothèque C++ Standard que vous utilisez du code natif.  
  
-   Corriger la gestion des exceptions unifiée dans les images pures et mixtes.  
  
-   Initialisation statique de variables C++ dans les images pures et mixtes.  
  
-   Prise en charge pour les variables par processus et par domaine d’application dans le code managé.  
  
-   Résout les problèmes de verrouillage du chargeur appliqués aux DLL mixtes compilés dans Visual Studio 2003 et versions antérieures.  
  
 En outre, cette prise en charge présente les limitations suivantes :  
  
-   Seul le modèle de la DLL CRT est pris en charge pour le code compilé avec/CLR.  
  
 Vous devez mettre à jour votre langage CLR (common runtime) vers la version actuelle comme il n’est pas garanti pour travailler avec les versions antérieures. Code généré avec ces modifications ne s’exécutera pas sur CLR version 1.x.  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)
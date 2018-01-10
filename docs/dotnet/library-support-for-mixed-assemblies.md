---
title: Prise en charge pour les assemblys mixtes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b3bc50416eceac64c134a31a4d7384e33db69b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="library-support-for-mixed-assemblies"></a>Prise en charge de bibliothèque pour les assemblys mixtes
Visual C++ prend en charge l’utilisation de la bibliothèque C++ Standard, la bibliothèque CRT, ATL et MFC pour les applications compilées avec [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md). Ainsi, les applications existantes qui utilisent ces bibliothèques à utiliser aussi bien les fonctionnalités de .NET Framework.  
  
 Cette prise en charge introduit les bibliothèques DLL et d’importation nouveau suivantes :  
  
-   Msvcmrt [d] .lib si vous compilez avec/CLR. Assemblys mixtes est lié à cette bibliothèque d’importation.  
  
-   Msvcm90 [d] .dll et Msvcurt [d] .lib si vous compilez avec/clr : pure. La DLL est un assembly mixte managé prise en charge des temps d’exécution C (CRT) et fait partie d’un assembly managé installé dans le global assembly cache (GAC). Assemblys purs se lient à cette bibliothèque d’importation et finissent liés à Msvcm90.dll.  
  
 Cette prise en charge offre que plusieurs avantages connexes :  
  
-   Le CRT et la bibliothèque C++ Standard sont disponibles pour le code mixte et pure. Le CRT et la bibliothèque C++ Standard fournis ne sont pas vérifiables ; Finalement, vos appels sont encore routés aux mêmes CRT et bibliothèque C++ Standard que vous utilisez du code natif.  
  
-   Corriger la gestion des exceptions unifiée dans les images pures et mixtes.  
  
-   Initialisation statique de variables C++ dans les images pures et mixtes.  
  
-   Prise en charge pour les variables par processus et par domaine d’application dans le code managé.  
  
-   Résout les problèmes de verrouillage du chargeur appliqués aux DLL mixtes compilés dans Visual Studio 2003 et versions antérieures.  
  
 En outre, cette prise en charge présente les limitations suivantes :  
  
-   Seul le modèle de la DLL CRT est pris en charge (à la fois pour le code compilé avec /clr ou/CLR : pure).  
  
-   Vous ne pouvez pas mélanger des objets purs et mixtes dans une seule image si ces objets utilisent les bibliothèques Visual C++ (étant donné que tous les objets doivent être purs dans une image pure). Si vous faites cela, vous recevez des erreurs au moment de la liaison.  
  
 Vous devez mettre à jour votre langage CLR (common runtime) vers la version actuelle comme il n’est pas garanti pour travailler avec les versions antérieures. Code généré avec ces modifications ne s’exécutera pas sur CLR version 1.x.  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)
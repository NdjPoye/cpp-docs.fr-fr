---
title: "Spécification de l’optimisation du compilateur pour un projet ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: abdad4367e75c1971ba5d11af1a60992d1bb3dd4
ms.lasthandoff: 02/24/2017

---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Spécification de l’optimisation du compilateur pour un projet ATL
Par défaut, le [Assistant contrôle ATL](../../atl/reference/atl-control-wizard.md) génère les nouvelles classes avec la macro ATL_NO_VTABLE, comme suit :  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 ATL définit ensuite _ATL_NO_VTABLE de la manière suivante :  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 Si vous ne définissez pas _ATL_DISABLE_NO_VTABLE, la macro ATL_NO_VTABLE se développe en `declspec(novtable)`. À l’aide de `declspec(novtable)`dans une classe déclaration empêche le pointeur vtable ne soit initialisé dans le constructeur de classe et le destructeur. Lorsque vous générez votre projet, l’éditeur de liens élimine la vtable et toutes les fonctions vers lequel pointe la vtable.  
  
 Vous devez utiliser ATL_NO_VTABLE et par conséquent `declspec(novtable)`, avec uniquement les classes de base qui ne peuvent pas être créées directement. Vous ne devez pas utiliser `declspec(novtable)` avec la classe la plus dérivée dans votre projet, car cette classe (généralement [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), ou [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) initialise le pointeur vtable pour votre projet.  
  
 Vous ne devez appeler les fonctions virtuelles à partir du constructeur d’un objet qui utilise `declspec(novtable)`. Vous devez déplacer ces appels vers le [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) méthode.  

  
 Si vous ne savez pas si vous devez utiliser le `declspec(novtable)` modificateur, vous pouvez supprimer la macro ATL_NO_VTABLE dans une définition de classe, ou vous pouvez globalement le désactiver en spécifiant  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 dans le fichier stdafx.h, fichiers d’en-tête sont incluses avant tous les autres ATL.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l’aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le Code C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Principes de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)



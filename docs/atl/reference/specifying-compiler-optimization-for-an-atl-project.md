---
title: "Sp&#233;cification de l&#39;optimisation du compilateur pour un projet ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.optimization"
  - "vc.appwiz.ATL.vtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, optimisation du compilateur"
  - "ATL_DISABLE_NO_VTABLE (macro)"
  - "ATL_NO_VTABLE (macro)"
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cification de l&#39;optimisation du compilateur pour un projet ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Par défaut, l'[Assistant Contrôle ATL](../../atl/reference/atl-control-wizard.md) génère les nouvelles classes avec la macro ATL\_NO\_VTABLE, comme indiqué ci\-après :  
  
```  
class ATL_NO_VTABLE CProjName  
{  
   ...  
};  
```  
  
 ATL définit ensuite \_ATL\_NO\_VTABLE de la manière suivante :  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
   #define ATL_NO_VTABLE  
#else  
   #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 Si vous ne définissez pas \_ATL\_DISABLE\_NO\_VTABLE, la macro ATL\_NO\_VTABLE s'exécute jusqu'à `declspec(novtable)`.  L'utilisation de `declspec(novtable)`dans une déclaration de classe empêche que le pointeur vtable ne soit initialisé dans le constructeur et le destructeur de la classe.  Lors de la génération de votre projet, l'éditeur de liens enlève le pointeur vtable et toutes les fonctions vers lesquelles il pointe.  
  
 Vous ne devez utiliser ATL\_NO\_VTABLE, et donc `declspec(novtable)`, que pour des classes de base qui ne peuvent pas être créées directement.  Vous ne devez pas utiliser `declspec(novtable)` avec la classe la plus dérivée dans votre projet, car cette classe \(généralement [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md) ou [CComPolyObject](../../atl/reference/ccompolyobject-class.md)\) initialise le pointeur vtable pour votre projet.  
  
 Vous ne devez pas non plus appeler des fonctions virtuelles à partir du constructeur d'un objet qui utilise `declspec(novtable)`.  Transférez ces appels à la méthode [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md).  
  
 Si vous ne savez pas si vous devez ou non utiliser le modificateur `declspec(novtable)`, vous pouvez supprimer la macro ATL\_NO\_VTABLE dans une définition de classe ou bien désactiver cette macro de façon globale en spécifiant la ligne de code  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 dans le fichier stdafx.h, avant l'ajout de tous les autres fichiers d'en\-tête ATL.  
  
## Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)
---
title: Rendre un objet ATL comme Noncreatable | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: b812c2d4bfeb0663d62051c05829f25dc7139faf
ms.lasthandoff: 02/24/2017

---
# <a name="making-an-atl-object-noncreatable"></a>Rendre un objet ATL comme Noncreatable
Vous pouvez modifier les attributs d’un objet COM fondés sur ATL afin qu’un client ne peut pas créer directement l’objet. Dans ce cas, l’objet est retourné via un appel de méthode sur un autre objet plutôt que créée directement.  
  
### <a name="to-make-an-object-noncreatable"></a>Pour rendre un objet comme noncreatable  
  
1.  Supprimer le [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) pour l’objet. Si vous souhaitez que l’objet comme noncreatable mais le contrôle, remplacez OBJECT_ENTRY_AUTO avec [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1).  
  
2.  Ajouter la [noncreatable](../../windows/noncreatable.md) attribut la coclasse dans le fichier .idl. Exemple :  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l’aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le Code C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Principes de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)



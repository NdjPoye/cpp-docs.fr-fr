---
title: Type de conversion des objets de classe MFC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros, type casting
- pointers, type casting
- type casts
- casting types
- macros, casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f1ae094e7085017f03daab3f73323da13ab1be39
ms.lasthandoff: 02/24/2017

---
# <a name="type-casting-of-mfc-class-objects"></a>Cast de type des objets de classe MFC
Macros de conversion de type permettent d’effectuer un cast de pointeur donné en pointeur qui pointe vers un objet de classe spécifique, avec ou sans vérifier que la conversion est autorisée.  
  
 Le tableau suivant répertorie les macros de conversion de type MFC.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Macros casté pointeurs vers des objets de classe MFC  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Convertit un pointeur vers un pointeur vers un objet de classe lors de la vérification pour voir si le cast est valide.|  
|[STATIC_DOWNCAST](#static_downcast)|Convertit un pointeur vers un objet d’une classe à un pointeur d’un type connexe. Dans une version debug, entraîne une **ASSERT** si l’objet n’est pas un « type de » le type cible.|  
  
##  <a name="a-namedynamicdowncasta--dynamicdowncast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 Fournit un moyen pratique d’effectuer un cast d’un pointeur vers un pointeur vers un objet de classe lors de la vérification pour voir si le cast est valide.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Paramètres  
 `class`  
 Le nom d’une classe.  
  
 `pointer`  
 Un pointeur pour être converti en un pointeur vers un objet de type `class`.  
  
### <a name="remarks"></a>Remarques  
 La macro sera effectué le `pointer` paramètre en un pointeur vers un objet de la `class` type de paramètre.  
  
 Si l’objet référencé par le pointeur est un « type de » la classe identifiée, la macro retourne le pointeur approprié. Si elle n’est pas un cast juridique, elle retourne **NULL**.  
  
##  <a name="a-namestaticdowncasta--staticdowncast"></a><a name="static_downcast"></a>STATIC_DOWNCAST  
 Les casts *pobject* vers un pointeur vers un *class_name* objet.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom de la classe en cours de conversion.  
  
 *pObject*  
 Le pointeur d’être converti en un pointeur vers un *class_name* objet.  
  
### <a name="remarks"></a>Remarques  
 *pObject* doit être **NULL**, ou pointer vers un objet d’une classe dérivée directement ou indirectement, à partir de *class_name*. Dans les versions de votre application avec le **_DEBUG** préprocesseur symbole est défini, la macro sera **ASSERT** si *pobject* n’est pas **NULL**, ou s’il pointe vers un objet qui n’est pas un « de » de la classe spécifiée dans le *class_name* paramètre (voir [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). Non- **_DEBUG** builds, la macro exécute le cast sans vérification du type.  
  
 La classe spécifiée dans le *class_name* paramètre doit être dérivé `CObject` et doivent utiliser le `DECLARE_DYNAMIC` et `IMPLEMENT_DYNAMIC`, le `DECLARE_DYNCREATE` et `IMPLEMENT_DYNCREATE`, ou `DECLARE_SERIAL` et `IMPLEMENT_SERIAL` macros comme expliqué dans l’article [CObject (classe) : dérivant une classe de CObject](../../mfc/deriving-a-class-from-cobject.md).  
  
 Par exemple, vous pouvez caster un pointeur vers `CMyDoc`, appelé `pMyDoc`, vers un pointeur vers **CDocument** en utilisant cette expression :  
  
 [!code-cpp[NVC_MFCDocView&#197;](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Si `pMyDoc` ne pointe pas vers un objet dérivé directement ou indirectement de **CDocument**, la macro sera **ASSERT**.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)


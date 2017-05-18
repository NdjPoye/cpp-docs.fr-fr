---
title: "Macros de table de l’objet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f03ca61c6ab3c550c316b380d34eb5fa4f3b61de
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="object-map-macros"></a>Macros de mappage d’objet
Ces macros définissent les mappages d’objet et les entrées.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Permet de spécifier la description de texte d’un objet de classe, qui sera entrée dans la table des objets.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Insère un objet ATL dans la table des objets, met à jour le Registre et crée une instance de l’objet.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Vous pouvez spécifier que l'objet doit être enregistré et initialisé, mais il ne doit pas pouvoir être créé en externe via `CoCreateInstance`.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 Permet de spécifier une description pour votre objet de classe.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Description de l’objet de la classe.  
  
### <a name="remarks"></a>Remarques  
 ATL accède à cette description dans la table d’objets via les [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) macro.  
  
 `DECLARE_OBJECT_DESCRIPTION`implémente une `GetObjectDescription` (fonction), qui vous permet de substituer le [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) (méthode).  

  
 Le `GetObjectDescription` fonction est appelée par **IComponentRegistrar::GetComponents**. **IComponentRegistrar** est une interface Automation qui vous permet d’inscrire et désinscrire des composants individuels dans une DLL. Lorsque vous créez un objet de l’inscription de composants avec l’Assistant Projet ATL, l’Assistant appliquent automatiquement la **IComponentRegistrar** interface. **IComponentRegistrar** est généralement utilisée par Microsoft Transaction Server.  
  
 Pour plus d’informations sur l’Assistant Projet ATL, consultez l’article [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#123;](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 Insère un objet ATL dans la table des objets, met à jour le Registre et crée une instance de l’objet.  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 [in] CLSID d'une classe COM implémentée par la classe C++ nommée `class`.  
  
 `class`  
 [in] Nom de la classe C++ qui implémente la classe COM représentée par `clsid`.  
  
### <a name="remarks"></a>Remarques  
 Les macros d'entrées d'objet sont placées au niveau de la portée globale dans le projet pour assurer la prise en charge de l'inscription, de l'initialisation et de la création d'une classe.  
  
 `OBJECT_ENTRY_AUTO`Insère les pointeurs de fonction de la classe de créateur et d’une classe de fabrique de classe créateur `CreateInstance` fonctions pour cet objet dans le mappage d’objets ATL généré automatiquement. Lors de la [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) est appelée, elle met à jour le Registre système pour chaque objet du mappage d’objets.  

  
 Le tableau ci-dessous décrit comment les informations ajoutées à la table d’objets sont obtenues à partir de la classe comme deuxième paramètre à cette macro.  
  
|Pour plus d’informations|Obtenu à partir de|  
|---------------------|-------------------|  
|Inscription de COM|[Macros de Registre](../../atl/reference/registry-macros.md)|  
|Création de fabrique de classe|[Macros de fabrique de classe](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Création d’une instance|[Macros d’agrégation](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Enregistrement de catégorie de composant|[Macros de catégorie](../../atl/reference/category-macros.md)|  
|Nettoyage et l’initialisation de niveau classe|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
 Vous pouvez spécifier que l'objet doit être enregistré et initialisé, mais il ne doit pas pouvoir être créé en externe via `CoCreateInstance`.  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 [in] CLSID d'une classe COM implémentée par la classe C++ nommée `class`.  
  
 `class`  
 [in] Nom de la classe C++ qui implémente la classe COM représentée par `clsid`.  
  
### <a name="remarks"></a>Notes  
 Les macros d'entrées d'objet sont placées au niveau de la portée globale dans le projet pour assurer la prise en charge de l'inscription, de l'initialisation et de la création d'une classe.  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`Vous pouvez spécifier qu’un objet doit être enregistré et initialisé (voir [OBJECT_ENTRY_AUTO](#object_entry_auto) pour plus d’informations), mais il ne doit pas être peut être créé via `CoCreateInstance`.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)


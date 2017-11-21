---
title: "Macros de l’objet du composant logiciel enfichable | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
dev_langs: C++
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b70a8e3d644389bcfb21b276c5a3bcfad84891a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="snap-in-object-macros"></a>Macros de l’objet du composant logiciel enfichable
Ces macros fournissent la prise en charge pour les extensions du composant logiciel enfichable.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Marque le début de l’extension du composant logiciel enfichable classe du mappage de données pour un objet de composant logiciel enfichable.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Marque le début de la carte de la barre d’outils pour un objet de composant logiciel enfichable.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Marque la fin de l’extension du composant logiciel enfichable classe du mappage de données pour un objet de composant logiciel enfichable.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Marque la fin de la carte de la barre d’outils pour un objet de composant logiciel enfichable.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Crée un membre de données pour la classe de données de l’extension composant logiciel enfichable.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Passe à une classe de données d’extension du composant logiciel enfichable dans le mappage de classe de données extension composant logiciel enfichable de l’objet du composant logiciel enfichable.|  
|[SNAPINMENUID](#snapinmenuid)|Déclare l’ID du menu contextuel utilisé par l’objet.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Insère une barre d’outils dans le mappage de la barre d’outils de l’objet du composant logiciel enfichable.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Marque le début de l’extension du composant logiciel enfichable classe du mappage de données.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Paramètres  
 *classname*  
 [in] Le nom de la classe de données d’extension du composant logiciel enfichable.  
  
### <a name="remarks"></a>Remarques  
 Démarrer votre mappage d’extension du composant logiciel enfichable avec la `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` (macro), ajouter des entrées pour chacun de vos types de données d’extension du composant logiciel enfichable avec la [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) (macro) et effectuer un mappage avec le [END_ EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) (macro).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP  
 Déclare le début de la carte d’ID de barre d’outils pour l’objet.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Paramètres  
 `_class`  
 [in] Spécifie la classe d’objet composant logiciel enfichable.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Marque la fin de l’extension du composant logiciel enfichable classe du mappage de données.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Remarques  
 Démarrez votre mappage d’extension du composant logiciel enfichable avec la [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) (macro), ajouter des entrées pour chacun de vos types de données du composant logiciel enfichable d’extension avec la [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) (macro), effectuez le mappage avec le `END_EXTENSION_SNAPIN_NODEINFO_MAP` (macro).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP  
 Déclare la fin de la carte d’ID de barre d’outils pour l’objet.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Paramètres  
 `_class`  
 [in] Spécifie la classe d’objet composant logiciel enfichable.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS  
 Ajoute un membre de données à la classe de données d’extension du composant logiciel enfichable pour un **ISnapInItemImpl**-classe dérivée.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Paramètres  
 `dataClass`  
 [in] La classe de données de l’extension composant logiciel enfichable.  
  
### <a name="remarks"></a>Remarques  
 Cette classe doit également être consignée dans un mappage de classe de données de composant logiciel enfichable extension. Démarrez votre mappage de classe de données de composant logiciel enfichable extension avec le [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) (macro), ajouter des entrées pour chacun de vos types de données d’extension du composant logiciel enfichable avec la [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)(macro) et effectuer un mappage avec le [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) (macro).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Ajoute une classe de données d’extension du composant logiciel enfichable pour le mappage de classe de données de composant logiciel enfichable extension.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Paramètres  
 `dataClass`  
 [in] La classe de données de l’extension composant logiciel enfichable.  
  
### <a name="remarks"></a>Remarques  
 Démarrer votre mappage de classe de données de composant logiciel enfichable extension avec le [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) (macro), ajouter des entrées pour chacun de vos types de données d’extension du composant logiciel enfichable avec la `EXTENSION_SNAPIN_NODEINFO_ENTRY` (macro) et effectuer un mappage avec le [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) (macro).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>SNAPINMENUID  
 Utilisez cette macro pour déclarer la ressource de menu contextuel de l’objet du composant logiciel enfichable.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identifie le menu contextuel de l’objet du composant logiciel enfichable.  
  
##  <a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY  
 Utilisez cette macro à entrer un ID de barre d’outils dans l’ID map barre d’outils du composant logiciel enfichable de l’objet.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Paramètres  
 `id`  
 [in] Identifie le contrôle de barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 Le [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) macro marque le début de la carte d’ID de barre d’outils ; le [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) macro marque la fin.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)

---
title: Macros de Registre | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a3abf5ad29b50c7f6708f02fd7c5aa193b3591c
ms.lasthandoff: 02/24/2017

---
# <a name="registry-macros"></a>Macros de Registre
Ces macros définissent les fonctionnalités de bibliothèque et de Registre de type utile.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY À](#_atl_static_registry)|Indique que vous souhaitez que le code d’inscription de votre objet se trouve dans l’objet afin d’éviter une dépendance sur ATL. DLL.|  
|[DECLARE_LIBID](#declare_libid)|Fournit un moyen de ATL obtenir le *libid* de la bibliothèque de types.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Évite l’inscription ATL par défaut.|  
|[DECLARE_REGISTRY](#declare_registry)|Insère ou supprime l’entrée de l’objet principal dans le Registre système.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Spécifie les informations requises pour inscrire automatiquement le *appid*.|  
|[MACRO DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Recherche de la ressource nommée et exécute le script de Registre qu’il contient.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Recherche de la ressource identifiée par un numéro d’ID et exécute le script de Registre qu’il contient.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
    
##  <a name="a-nameatlstaticregistrya--atlstaticregistry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY À  
 Un symbole qui indique que vous souhaitez que le code d’inscription de votre objet se trouve dans l’objet afin d’éviter une dépendance sur ATL. DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Notes  
 Lorsque vous définissez **ATL_STATIC_REGISTRY**, vous devez utiliser le code suivant :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample n °&5;](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="a-namedeclarelibida--declarelibid"></a><a name="declare_libid"></a>DECLARE_LIBID  
 Fournit un moyen de ATL obtenir le *libid* de la bibliothèque de types.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Paramètres  
 *LIBID*  
 Le GUID de la bibliothèque de types.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `DECLARE_LIBID` dans un `CAtlModuleT`-classe dérivée.  
  
### <a name="example"></a>Exemple  
 Avec attributs générées par l’Assistant ATL (projets) auront un exemple d’utilisation de cette macro.  
  
##  <a name="a-namedeclarenoregistrya--declarenoregistry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY  
 Utilisez `DECLARE_NO_REGISTRY` si vous souhaitez éviter toute inscription ATL par défaut pour la classe dans laquelle cette macro apparaît.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="a-namedeclareregistrya--declareregistry"></a><a name="declare_registry"></a>DECLARE_REGISTRY  
 Passe à l’inscription de classe standard dans le Registre du système ou le supprime du Registre système.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>Paramètres  
 `class`  
 [in] Inclus pour la compatibilité descendante.  
  
 `pid`  
 [in] Un `LPCTSTR` qui est un identificateur de programme de version spécifique.  
  
 *vpid*  
 [in] Un `LPCTSTR` qui est un identificateur de programme indépendant de la version.  
  
 *NID*  
 [in] A **UINT** qui est un index de la chaîne de ressource dans le Registre pour utiliser la description du programme.  
  
 `flags`  
 [in] Un `DWORD` contenant le programme de thread du modèle dans le Registre. Doit être une des valeurs suivantes : **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, ou **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Remarques  
 L’enregistrement standard se compose des CLSID, ID de programme, identifiant indépendant de la version du programme, chaîne de description et modèle de thread.  
  
 Lorsque vous créez un objet ou contrôler à l’aide de l’Assistant Ajout de classes ATL, l’Assistant implémente la prise en charge du Registre basée sur le script automatiquement et ajoute les [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) macro pour vos fichiers. Si vous ne souhaitez pas de prise en charge du Registre basée sur un script, vous devez remplacer cette macro avec `DECLARE_REGISTRY`. `DECLARE_REGISTRY`insère uniquement les cinq clés de base décrits ci-dessus dans le Registre. Vous devez écrire manuellement le code pour insérer les autres clés dans le Registre.  
  
##  <a name="a-namedeclareregistryappidresourceida--declareregistryappidresourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID  
 Spécifie les informations requises pour inscrire automatiquement le *appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Paramètres  
 *RESID*  
 L’id de ressource du fichier .rgs qui contient des informations sur le *appid*.  
  
 *AppID*  
 GUID.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `DECLARE_REGISTRY_APPID_RESOURCEID` dans un `CAtlModuleT`-classe dérivée.  
  
### <a name="example"></a>Exemple  
 Classes ajoutées aux projets ATL avec l’Assistant Ajouter une classe du code aura un exemple d’utilisation de cette macro.  
  
##  <a name="a-namedeclareregistryresourcea--declareregistryresource"></a><a name="declare_registry_resource"></a>MACRO DECLARE_REGISTRY_RESOURCE  
 Obtient la ressource nommée contenant le fichier de Registre et exécute le script pour entrer des objets dans le Registre système ou les supprimer à partir du Registre système.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Identificateur de votre ressource de chaîne.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous créez un objet ou contrôler à l’aide de l’Assistant Projet ATL, l’Assistant implémenter la prise en charge du Registre basée sur le script et automatiquement ajouter la [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) (macro), qui est similaire à `DECLARE_REGISTRY_RESOURCE`, à vos fichiers.  
  
 Vous pouvez lier statiquement avec le composant de Registre ATL (inscription) pour accéder au Registre optimisé. Pour créer un lien statique avec le code Registrar, ajoutez la ligne suivante dans votre fichier stdafx.h :  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Si vous souhaitez ATL pour remplacer les valeurs de remplacement au moment de l’exécution, ne spécifiez pas le `DECLARE_REGISTRY_RESOURCE` ou `DECLARE_REGISTRY_RESOURCEID` (macro). Au lieu de cela, créez un tableau de **_ATL_REGMAP_ENTRIES** des structures, où chaque entrée contient un espace réservé de variable associée à une valeur à remplacer l’espace réservé au moment de l’exécution. Appelez ensuite [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) ou [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), en passant le tableau. Cela ajoute toutes les valeurs de remplacement dans le **_ATL_REGMAP_ENTRIES** structures au mappage de remplacement du bureau d’enregistrement.  

  
 Pour plus d’informations sur les paramètres remplaçables et les scripts, consultez l’article [le composant de Registre ATL (inscription)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="a-namedeclareregistryresourceida--declareregistryresourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID  
 Identique à [macro DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) sauf qu’elle utilise un générées par l’Assistant **UINT** pour identifier la ressource, plutôt qu’un nom de chaîne.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Identificateur généré par l’Assistant de votre ressource.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous créez un objet ou contrôler à l’aide de l’Assistant Projet ATL, l’Assistant implémenter la prise en charge du Registre basée sur le script et automatiquement ajouter la `DECLARE_REGISTRY_RESOURCEID` macro pour vos fichiers.  
  
 Vous pouvez lier statiquement avec le composant de Registre ATL (inscription) pour accéder au Registre optimisé. Pour créer un lien statique avec le code Registrar, ajoutez la ligne suivante dans votre fichier stdafx.h :  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Si vous souhaitez ATL pour remplacer les valeurs de remplacement au moment de l’exécution, ne spécifiez pas le `DECLARE_REGISTRY_RESOURCE` ou `DECLARE_REGISTRY_RESOURCEID` (macro). Au lieu de cela, créez un tableau de **_ATL_REGMAP_ENTRIES** des structures, où chaque entrée contient un espace réservé de variable associée à une valeur à remplacer l’espace réservé au moment de l’exécution. Appelez ensuite [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) ou [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), en passant le tableau. Cela ajoute toutes les valeurs de remplacement dans le **_ATL_REGMAP_ENTRIES** structures au mappage de remplacement du bureau d’enregistrement.  

  
 Pour plus d’informations sur les paramètres remplaçables et les scripts, consultez l’article [le composant de Registre ATL (inscription)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)


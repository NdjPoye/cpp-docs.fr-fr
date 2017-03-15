---
title: Fonctions globales de Registre et TypeLib | Documents Microsoft
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
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
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
ms.openlocfilehash: 9d454f2eac1b29785fe40a480fc43c7c34a861a3
ms.lasthandoff: 02/24/2017

---
# <a name="registry-and-typelib-global-functions"></a>Fonctions globales du Registre et de TypeLib
Ces fonctions fournissent la prise en charge pour le chargement et l’inscription d’une bibliothèque de types.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans les tableaux suivants ne peuvent pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](#atlregistertypelib)|Cette fonction est appelée pour inscrire une bibliothèque de types.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Cette fonction est appelée pour annuler l’inscription d’une bibliothèque de types|  
|[AtlLoadTypeLib](#atlloadtypelib)|Cette fonction est appelée pour charger une bibliothèque de types.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Cette fonction est appelée pour mettre à jour le Registre à partir de la ressource fournie.|  
|[RegistryDataExchange](#registrydataexchange)|Cette fonction est appelée pour lire ou écrire dans le Registre système. Appelée par le [Macros d’échange de données de Registre](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Ces fonctions contrôlent quel nœud dans le Registre, le programme utilise pour stocker les informations.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Récupère si l’application redirige l’accès au Registre vers le **HKEY_CURRENT_USER** ( **HKCU**) nœud.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Définit si l’application redirige l’accès au Registre vers le **HKEY_CURRENT_USER** ( **HKCU**) nœud.|  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h

## <a name="a-nameatlgetperuserregistrationa-atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
Utilisez cette fonction pour déterminer si l’application redirige l’accès au Registre vers le **HKEY_CURRENT_USER** (**HKCU**) nœud.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `pEnabled`  
 `TRUE`Indique que les informations du Registre sont dirigées vers le **HKCU** nœud ; `FALSE` indique que l’application écrit les informations du Registre dans le nœud par défaut. Le nœud par défaut est **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Valeur de retour  
 `S_OK`Si la méthode réussite, sinon le `HRESULT` code d’erreur si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 La redirection du Registre n’est pas activée par défaut. Si vous activez cette option, l’accès au Registre est redirigé vers **HKEY_CURRENT_USER\Software\Classes**.  
  
 La redirection n’est pas globale. Seuls les infrastructures MFC et ATL sont affectés par cette redirection de Registre.  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  

##  <a name="a-nameatlregistertypeliba--atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 Cette fonction est appelée pour inscrire une bibliothèque de types.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstTypeLib`  
 Handle de l’instance du module.  
  
 `lpszIndex`  
 Chaîne au format «\\\N », où N est l’index d’entiers de la ressource de bibliothèque de type. Valeur peut être NULL si aucun index n’est requis.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction d’assistance utilisée par [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) et [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h

## <a name="a-nameatlsetperuserregistrationa-atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
Définit si l’application redirige l’accès au Registre vers le **HKEY_CURRENT_USER** (**HKCU**) nœud.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Indique que les informations du Registre sont dirigées vers le **HKCU** nœud ; `FALSE` indique que l’application écrit les informations du Registre dans le nœud par défaut. Le nœud par défaut est **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Valeur de retour  
 `S_OK`Si la méthode réussite, sinon le `HRESULT` code d’erreur si une erreur se produit.  
  
### <a name="remarks"></a>Remarques  
 La redirection du Registre n’est pas activée par défaut. Si vous activez cette option, l’accès au Registre est redirigé vers **HKEY_CURRENT_USER\Software\Classes**.  
  
 La redirection n’est pas globale. Seuls les infrastructures MFC et ATL sont affectés par cette redirection de Registre.  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  

##  <a name="a-nameatlunregistertypeliba--atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
 Cette fonction est appelée pour annuler l'inscription d'une bibliothèque de types.  
  
### <a name="syntax"></a>Syntaxe  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstTypeLib`  
 Handle de l’instance du module.  
  
 `lpszIndex`  
 Chaîne au format «\\\N », où N est l’index d’entiers de la ressource de bibliothèque de type. Valeur peut être NULL si aucun index n’est requis.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction d’assistance utilisée par [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) et [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h

##  <a name="a-nameatlloadtypeliba--atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib  
 Cette fonction est appelée pour charger une bibliothèque de types.  
  
### <a name="syntax"></a>Syntaxe  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstTypeLib`  
 Handle vers le module associé à la bibliothèque de types.  
  
 `lpszIndex`  
 Chaîne au format «\\\N », où N est l’index d’entiers de la ressource de bibliothèque de type. Valeur peut être NULL si aucun index n’est requis.  
  
 *pbstrPath*  
 Lors d’un retour, contient le chemin d’accès complet du module associé à la bibliothèque de types.  
  
 `ppTypeLib`  
 Lors d’un retour, contient un pointeur vers un pointeur vers la bibliothèque de types chargés.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction d’assistance utilisée par [AtlRegisterTypeLib](#atlregistertypelib) et [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="a-nameatlupdateregistryfromresourceda--atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 Cette fonction a été déconseillée dans Visual Studio 2013 et supprimée dans Visual Studio 2015.  
  
```
<removed>
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameregistrydataexchangea--registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange  
 Cette fonction est appelée pour lire ou écrire dans le Registre système.  

### <a name="syntax"></a>Syntaxe  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *pT*  
 Pointeur vers l’objet actuel.  
  
 *rdxOp*  
 Une valeur d’énumération qui indique quelle opération la fonction doit effectuer. Consultez le tableau dans la section Notes pour les valeurs autorisées.  
  
 `pItem`  
 Pointeur vers les données qui doit être lu ou écrit dans le Registre. Les données peuvent également représenter une clé doit être supprimé à partir du Registre. La valeur par défaut est NULL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Les macros [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) et [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) développer à une fonction qui appelle `RegistryDataExchange`.  
  
 Les valeurs enum possibles qui indiquent que l’opération la fonction doit exécuter sont affichées dans le tableau suivant :  
  
|Valeur d’énumération|Opération|  
|----------------|---------------|  
|eReadFromReg|Données lues à partir du Registre.|  
|eWriteToReg|Écrire des données dans le Registre.|  
|eDeleteFromReg|Supprimer la clé du Registre.|  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h

## <a name="see-also"></a>Voir aussi  
 [Fonctions](atl-functions.md)
 [Macros d’échange de données de Registre](registry-data-exchange-macros.md)







---
title: Interface IRegistrar | Documents Microsoft
ms.custom: 
ms.date: 2/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRegistrar
- IRegistrar
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
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
ms.sourcegitcommit: 199cdfd91a7d1b9882b57118c852352f6fdda43e
ms.openlocfilehash: e73e095d253d5ec5ca53e4e446019b2da79e5d39
ms.lasthandoff: 02/24/2017

---
# <a name="iregistrar-interface"></a>Interface IRegistrar
Cette interface est définie dans atliface.h et est utilisée en interne par les fonctions membres de CAtlModule comme [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced).   
  
## <a name="syntax"></a>Syntaxe  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>Remarques
Consultez la rubrique [à l’aide des paramètres remplaçables (le préprocesseur de Registrar)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) pour plus de détails.  

## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Inscrit la ressource. |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Annule l’inscription de la ressource.|  
|[IRegistrar::FileRegister](#fileregister)|Enregistre le fichier.|  
|[IRegistrar::FileUnregister](#fileunregister)|Annule l’enregistrement du fichier.|  
|[IRegistrar::StringRegister](#stringregister)|Enregistre la chaîne.|  
|[IRegistrar::StringUnregister](#stringunregister)|Annule l’inscription de la chaîne|  
|[IRegistrar::ResourceRegister](#resourceregister)|Inscrit la ressource.|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|Annule l’inscription de la ressource.| 
  

 
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlifase.h  
  
##  <a name="a-nameresourceregistersza--iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz 
 Inscrit la ressource.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="a-nameresourceunregistersza--iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz  
 Annule l’inscription de la ressource.
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="a-namefileregistera--iregistrarfileregister"></a><a name="fileregister"></a>IRegistrar::FileRegister  
Enregistre le fichier.
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="a-namefileunregistera--iregistrarfileunregister"></a><a name="fileunregister"></a>IRegistrar::FileUnregister  
Annule l’enregistrement du fichier.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="a-namestringregistera--iregistrarstringregister"></a><a name="stringregister"></a>IRegistrar::StringRegister  
  Enregistre les données de la chaîne spécifiée.
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="a-namestringunregistera--iregistrarstringunregister"></a><a name="stringunregister"></a>IRegistrar::StringUnregister
 Annule l’enregistrement de données de type chaîne spécifiée.  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="a-nameresourceregistera--iregistrarresourceregister"></a><a name="resourceregister"></a>IRegistrar::ResourceRegister  
 Inscrit la ressource.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="a-nameresourceunregistera--iregistrarresourceunregister"></a><a name="resourceunregister"></a>IRegistrar::ResourceUnregister  
 Annule l’inscription de la ressource.  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>Voir aussi  
 [Utilisation de paramètres remplaçables (le préprocesseur de Registrar)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)   
 [Composant de Registre (inscription)](../../atl/atl-registry-component-registrar.md)  


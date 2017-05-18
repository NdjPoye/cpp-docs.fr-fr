---
title: Fonctions globales de marshaling | Documents Microsoft
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
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 19
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dd4b8d50ec69974b7b2af29438b1657e1ce592b4
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="marshaling-global-functions"></a>Marshaling des fonctions globales
Ces fonctions fournissent la prise en charge de marshaling et de conversion de données de marshaling des pointeurs d’interface.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Libère les données de marshaling et `IStream` pointeur.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Crée un objet de flux et marshale le pointeur d’interface spécifié.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Convertit les données de marshaling d’un flux en un pointeur d’interface.|  
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 Libère les données de marshaling dans le flux, puis libère le pointeur de flux.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 [in] Un pointeur vers le `IStream` interface sur le flux utilisé pour le marshaling.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
 Crée un objet de flux, écrit le CLSID du proxy dans le flux, puis marshale le pointeur d’interface spécifié en écrivant les données nécessaires pour initialiser le proxy dans le flux.  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnk*  
 [in] Pointeur vers l’interface à marshaler.  
  
 `iid`  
 [in] Le GUID de l’interface qui est marshalé.  
  
 `ppStream`  
 [out] Un pointeur vers le `IStream` interface sur l’objet de flux utilisé pour le marshaling.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 Le **MSHLFLAGS_TABLESTRONG** est défini pour le pointeur peut être marshalé en plusieurs flux de données. Le pointeur peut également être démarshalé plusieurs fois.  
  
 Marshaling échoue, le pointeur de flux est libéré.  
  
 `AtlMarshalPtrInProc`peut être utilisé uniquement sur un pointeur vers un objet dans le processus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#50;](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
 Convertit les données de marshaling du flux en un pointeur d’interface qui peut être utilisé par le client.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 [in] Pointeur vers le flux en cours démarshalée.  
  
 `iid`  
 [in] Le GUID de l’interface démarshalée en cours.  
  
 `ppUnk`  
 [out] Pointeur vers l’interface démarshalé.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)


---
title: CDBErrorInfo::GetAllErrorInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs: C++
helpviewer_keywords: GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46e233800f814b39e4e14f0b357c381a3e71311e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
Retourne tous les types d’informations sur les erreurs contenues dans un enregistrement d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *ulRecordNum*  
 [in] Numéro de base zéro de l’enregistrement pour lequel retourner les informations d’erreur.  
  
 `lcid`  
 [in] L’ID de paramètres régionaux pour les informations d’erreur à retourner.  
  
 `pbstrDescription`  
 [out] Pointeur vers une description de l’erreur ou la valeur NULL si les paramètres régionaux ne sont pas pris en charge. Consultez la section Notes.  
  
 `pbstrSource`  
 [out] Un pointeur vers une chaîne contenant le nom du composant qui a généré l’erreur.  
  
 `pguid`  
 [out] Pointeur vers le GUID de l’interface ayant défini l’erreur.  
  
 *pdwHelpContext*  
 [out] Pointeur vers l’ID de contexte d’aide pour l’erreur.  
  
 *pbstrHelpFile*  
 [out] Un pointeur vers une chaîne contenant le chemin d’accès au fichier d’aide qui décrit l’erreur.  
  
## <a name="return-value"></a>Valeur de retour  
 `S_OK` si l'opération a réussi. Consultez [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) dans les *de référence du programmeur OLE DB* pour d’autres valeurs de retournés.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="remarks"></a>Notes  
 La valeur de sortie `pbstrDescription` est obtenu en interne en appelant IErrorInfo::GetDescription, qui définit la valeur null si les paramètres régionaux ne sont pas pris en charge, ou si les deux conditions suivantes sont remplies :  
  
1.  la valeur de `lcid` n’est pas des États-Unis Anglais et  
  
2.  la valeur de `lcid` est différent de la valeur retournée par GetUserDefaultLCID.  
  
## <a name="see-also"></a>Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)
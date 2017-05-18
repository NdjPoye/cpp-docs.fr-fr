---
title: "Inscription des contrôles OLE | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls, registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9c54fb7dc3802e78c8dc68df02ff55ef4732a36b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="registering-ole-controls"></a>Inscription des contrôles OLE
Contrôles OLE, comme les autres objets de serveur OLE, sont accessibles par d’autres applications prenant en charge OLE. Pour cela, vous devez inscrire la bibliothèque de types et de classe du contrôle.  
  
 Les fonctions suivantes permettent d’ajouter et de supprimer la classe du contrôle, de pages de propriétés et de bibliothèque de types dans la base de données d’inscription Windows :  
  
### <a name="registering-ole-controls"></a>Inscription des contrôles OLE  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Ajoute la classe du contrôle à la base de données d’inscription.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Ajoute une page de propriétés du contrôle à la base de données d’inscription.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Ajoute la bibliothèque de types du contrôle à la base de données d’inscription.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Supprime une classe de contrôle ou d’une classe de page de propriétés de la base de données d’inscription.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Supprime la bibliothèque de types du contrôle à partir de la base de données d’inscription.|  
  
 `AfxOleRegisterTypeLib`est généralement appelée dans l’implémentation d’une DLL de contrôle de `DllRegisterServer`. De même, `AfxOleUnregisterTypeLib` est appelée par `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, et `AfxOleUnregisterClass` sont généralement appelées par le `UpdateRegistry` fonction membre de la page de fabrique ou une propriété de classe d’un contrôle.  
  
##  <a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass  
 Enregistre la classe de contrôle avec la base de registres de Windows.  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 Le handle d’instance du module associé à la classe de contrôle.  
  
 `clsid`  
 L’ID de classe unique du contrôle.  
  
 `pszProgID`  
 L’identifiant unique du contrôle.  
  
 `idTypeName`  
 L’ID de ressource de la chaîne qui contient un nom de type lisible par l’utilisateur pour le contrôle.  
  
 *idBitmap*  
 L’ID de ressource de l’image utilisée pour représenter le contrôle OLE dans une barre d’outils ou une palette.  
  
 `nRegFlags`  
 Contient un ou plusieurs des indicateurs suivants :  
  
- `afxRegInsertable`Permet le contrôle s’affiche dans la boîte de dialogue Insérer un objet pour les objets OLE.  
  
- `afxRegApartmentThreading`Définit le modèle de thread dans le Registre pour ThreadingModel = cloisonnement.  
  
- `afxRegFreeThreading`Définit le modèle de thread dans le Registre pour ThreadingModel = gratuit.  
  
     Vous pouvez combiner les deux indicateurs `afxRegApartmentThreading` et `afxRegFreeThreading` pour définir ThreadingModel = les deux. Consultez la page [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur l’inscription du modèle de thread.  
  
> [!NOTE]
>  Dans les versions 4.2 de MFC, avant du `int` `nRegFlags` paramètre était un **BOOL** paramètre, *bInsertable*, qui autorisé ou interdit le contrôle à insérer à partir de la boîte de dialogue Insérer un objet.  
  
 *dwMiscStatus*  
 Contient un ou plusieurs des indicateurs d’état suivant (pour une description des indicateurs, consultez **OLEMISC** énumération dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]) :  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   OLEMISC_ACTIVATEWHENVISIBLE  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 ID unique de la classe de contrôle.  
  
 `wVerMajor`  
 Numéro de version principale de la classe de contrôle.  
  
 `wVerMinor`  
 Numéro de version secondaire de la classe de contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la classe de contrôle a été inscrit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cela permet le contrôle à utiliser par les conteneurs de contrôle OLE prenant en charge. `AfxOleRegisterControlClass`met à jour le Registre avec le nom du contrôle et l’emplacement sur le système et définit également le modèle de thread prenant en charge le contrôle dans le Registre. Pour plus d’informations, consultez [technique Remarque 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), « Modèle Apartment de thread dans OLE Controls, » et [sur les processus et Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAxCtl&#11;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 L’exemple ci-dessus illustre comment `AfxOleRegisterControlClass` est appelée avec l’indicateur pour insérer et l’indicateur de cloisonnement or pour créer le sixième paramètre de modèle :  
  
 [!code-cpp[NVC_MFCAxCtl&#12;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Le contrôle s’affichera dans la boîte de dialogue Insérer un objet pour les conteneurs activés, et il sera compatible avec le modèle de cloisonnement. Contrôles compatible avec le modèle de cloisonnement doivent garantir cette classe statique données sont protégées par des verrous, afin que pendant un contrôle dans un cloisonnement accède à des données statiques, il n’est pas désactivé par le planificateur avant la fin, et une autre instance de la même classe démarre en utilisant les mêmes données statiques. Tout accès aux données statiques sont entourées par le code de la section critique.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass  
 Enregistre la classe de page de propriétés avec la base de registres de Windows.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 Le handle d’instance du module associé à la classe de page de propriétés.  
  
 `clsid`  
 L’ID de classe unique de la page de propriétés.  
  
 `idTypeName`  
 L’ID de ressource de la chaîne qui contient un nom lisible par l’utilisateur pour la page de propriétés.  
  
 `nRegFlags`  
 Peut contenir l’indicateur :  
  
- `afxRegApartmentThreading`Définit le modèle de thread dans le Registre pour ThreadingModel = cloisonnement.  
  
> [!NOTE]
>  Dans les versions MFC avant 4.2 de MFC, la `int` `nRegFlags` paramètre n’était pas disponible. Notez également que le `afxRegInsertable` indicateur n’est pas une option valide pour les pages de propriétés et provoque une assertion dans MFC s’il est défini  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la classe de contrôle a été inscrit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Ainsi, la page de propriétés à utiliser par les conteneurs de contrôle OLE prenant en charge. `AfxOleRegisterPropertyPageClass`met à jour le Registre avec le nom de la page de propriété et son emplacement sur le système et définit également le modèle de thread prenant en charge le contrôle dans le Registre. Pour plus d’informations, consultez [technique Remarque 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), « Modèle Apartment de thread dans OLE Controls, » et [sur les processus et Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib  
 Inscrit la bibliothèque de types avec la base de données d’inscription de Windows et permet à la bibliothèque de types à utiliser par les autres conteneurs OLE-contrôle prenant en charge.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 Le handle d’instance de l’application associée à la bibliothèque de types.  
  
 *tlid*  
 ID unique de la bibliothèque de types.  
  
 *pszFileName*  
 Pointe vers le nom de fichier facultatif d’une bibliothèque de types localisée (. Fichier TLB) pour le contrôle.  
  
 *pszHelpDir*  
 Le nom du répertoire dans lequel vous pouvez trouver le fichier d’aide de la bibliothèque de types. Si **NULL**, le fichier d’aide est supposé être dans le même répertoire que la bibliothèque de type.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la bibliothèque de types a été inscrite ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction met à jour le Registre avec le nom et son emplacement sur le système.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAutomation&#7;](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation n °&8;](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>AfxOleUnregisterClass  
 Supprime l’entrée de classe de page de contrôle ou la propriété à partir de la base de registres de Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Paramètres  
 *clsID*  
 L’ID de classe unique de la page de contrôle ou la propriété.  
  
 `pszProgID`  
 ID unique du programme de la page de contrôle ou la propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la classe de page de contrôle ou la propriété a été correctement annulée ; sinon 0.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib  
 Appelez cette fonction pour supprimer l’entrée de bibliothèque de type de la base de registres de Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Paramètres  
 `tlID`  
 ID unique de la bibliothèque de types.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la bibliothèque de types a été correctement annulée ; sinon 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAxCtl&#13;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxdisp.h  

## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)


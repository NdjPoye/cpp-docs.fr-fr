---
title: Classe de CIPAddressCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
dev_langs:
- C++
helpviewer_keywords:
- IP address control
- Internet address edit box
- CIPAddressCtrl class
- Internet protocol address box
- common controls, Internet Explorer 4.0
- Internet Explorer 4.0 common controls
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
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
ms.openlocfilehash: b3849580c7bfd07f241e55cc48144959566d7d09
ms.lasthandoff: 02/24/2017

---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl (classe)
Fournit les fonctionnalités du contrôle commun d'adresse IP Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Construit un objet `CIPAddressCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Efface le contenu du contrôle d’adresse IP.|  
|[CIPAddressCtrl::Create](#create)|Crée un contrôle d’adresse IP et l’attache à une `CIPAddressCtrl` objet.|  
|[CIPAddressCtrl::CreateEx](#createex)|Crée un contrôle d’adresse IP avec les styles étendus Windows spécifiés et l’attache à une `CIPAddressCtrl` objet.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Récupère les valeurs d’adresse pour les quatre champs dans le contrôle d’adresse IP.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Détermine si le contrôle d’adresse IP de tous les champs sont vides.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Définit les valeurs pour les quatre champs d’adresse dans le contrôle d’adresse IP.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Définit le focus clavier sur le champ spécifié dans le contrôle d’adresse IP.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Définit la plage dans le champ spécifié dans le contrôle d’adresse IP.|  
  
## <a name="remarks"></a>Remarques  
 Un contrôle d’adresse IP, un contrôle similaire à un contrôle d’édition, permet d’entrer et de manipuler une adresse numérique format IP (Internet Protocol).  
  
 Ce contrôle (et par conséquent la `CIPAddressCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Microsoft Internet Explorer 4.0 et versions ultérieures. Elles seront également disponibles dans les versions futures de Windows et Windows NT.  
  
 Pour obtenir des informations plus générales sur le contrôle d’adresse IP, consultez [contrôles d’adresse IP](http://msdn.microsoft.com/library/windows/desktop/bb761372) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="a-namecipaddressctrla--cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl  
 Crée un objet `CIPAddressCtrl`.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="a-nameclearaddressa--cipaddressctrlclearaddress"></a><a name="clearaddress"></a>CIPAddressCtrl::ClearAddress  
 Efface le contenu du contrôle d’adresse IP.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreatea--cipaddressctrlcreate"></a><a name="create"></a>CIPAddressCtrl::Create  
 Crée un contrôle d’adresse IP et l’attache à une `CIPAddressCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Style du contrôle de l’adresse IP. Appliquer une combinaison de styles de fenêtre. Vous devez inclure le **WS_CHILD** de style, car le contrôle doit être une fenêtre enfant. Consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir la liste des styles de windows.  
  
 `rect`  
 Une référence à la taille et la position du contrôle d’adresse IP. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre du parent du contrôle d’adresse IP. Il ne doit pas être **NULL.**  
  
 `nID`  
 ID. du contrôle d’adresse IP  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous construisez un `CIPAddressCtrl` objet en deux étapes.  
  
1.  Appelez le constructeur, ce qui crée le `CIPAddressCtrl` objet.  
  
2.  Appelez **créer**, ce qui crée le contrôle d’adresse IP.  
  
 Si vous souhaitez utiliser les styles étendus windows avec votre contrôle, appelez [CreateEx](#createex) au lieu de **créer**.  
  
##  <a name="a-namecreateexa--cipaddressctrlcreateex"></a><a name="createex"></a>CIPAddressCtrl::CreateEx  
 Appelez cette fonction pour créer un contrôle (une fenêtre enfant) et y associer le `CIPAddressCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Style du contrôle de l’adresse IP. Appliquer une combinaison de styles de fenêtre. Vous devez inclure le **WS_CHILD** de style, car le contrôle doit être une fenêtre enfant. Consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir la liste des styles de windows.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="a-namegetaddressa--cipaddressctrlgetaddress"></a><a name="getaddress"></a>CIPAddressCtrl::GetAddress  
 Récupère les valeurs d’adresse pour les quatre champs dans le contrôle d’adresse IP.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>Paramètres  
 `nField0`  
 Une référence à la valeur 0 à partir d’une adresse IP compressée.  
  
 `nField1`  
 Une référence à la valeur du champ de 1 à partir d’une adresse IP compressée.  
  
 `nField2`  
 Une référence à la valeur du champ 2 à partir d’une adresse IP compressée.  
  
 `nField3`  
 Une référence à la valeur du champ 3 à partir d’une adresse IP compressée.  
  
 `dwAddress`  
 Une référence à l’adresse d’un `DWORD` valeur qui reçoit l’adresse IP. Consultez la page **remarques** pour une table qui montre comment `dwAddress` est rempli.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de champs non vide dans le contrôle d’adresse IP.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans le premier prototype ci-dessus, les chiffres de 0 à 3 du contrôle, les champs lues de gauche à droite respectivement, remplir les quatre paramètres. Dans le deuxième prototype ci-dessus, `dwAddress` est rempli comme suit.  
  
|Champ|Contenant la valeur du champ de bits|  
|-----------|-------------------------------------|  
|0|24 à 31|  
|1|16 à 23|  
|2|8 à 15|  
|3|0 à 7|  
  
##  <a name="a-nameisblanka--cipaddressctrlisblank"></a><a name="isblank"></a>CIPAddressCtrl::IsBlank  
 Détermine si le contrôle d’adresse IP de tous les champs sont vides.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si tous les champs de contrôle de l’adresse IP sont vides ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetaddressa--cipaddressctrlsetaddress"></a><a name="setaddress"></a>CIPAddressCtrl::SetAddress  
 Définit les valeurs pour les quatre champs d’adresse dans le contrôle d’adresse IP.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>Paramètres  
 `nField0`  
 La valeur du champ 0 à partir d’une adresse IP compressée.  
  
 `nField1`  
 La valeur du champ de 1 à partir d’une adresse IP compressée.  
  
 `nField2`  
 La valeur du champ 2 à partir d’une adresse IP compressée.  
  
 `nField3`  
 La valeur du champ 3 à partir d’une adresse IP compressée.  
  
 `dwAddress`  
 Un `DWORD` valeur qui contient la nouvelle adresse IP. Consultez **remarques** pour une table qui montre comment la `DWORD` valeur est renseignée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans le premier prototype ci-dessus, les chiffres de 0 à 3 du contrôle, les champs lues de gauche à droite respectivement, remplir les quatre paramètres. Dans le deuxième prototype ci-dessus, `dwAddress` est rempli comme suit.  
  
|Champ|Contenant la valeur du champ de bits|  
|-----------|-------------------------------------|  
|0|24 à 31|  
|1|16 à 23|  
|2|8 à 15|  
|3|0 à 7|  
  
##  <a name="a-namesetfieldfocusa--cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus  
 Définit le focus clavier sur le champ spécifié dans le contrôle d’adresse IP.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Paramètres  
 `nField`  
 Index du champ de base zéro à laquelle le focus doit être défini. Si cette valeur est supérieure au nombre de champs, est activé pour le premier champ vide. Si tous les champs sont non vide, est activé pour le premier champ.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetfieldrangea--cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange  
 Définit la plage dans le champ spécifié dans le contrôle d’adresse IP.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Paramètres  
 `nField`  
 Index des champs de base zéro auquel la plage s’appliquera.  
  
 `nLower`  
 Une référence à un entier de réception de la limite inférieure du champ spécifié dans ce contrôle d’adresse IP.  
  
 `nUpper`  
 Une référence à un entier de réception de la limite supérieure du champ spécifié dans ce contrôle d’adresse IP.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Utilisez les deux paramètres, `nLower` et `nUpper`, pour indiquer les limites inférieures et supérieures du champ, à la place de la *wRange* paramètre utilisé avec le message Win32.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)





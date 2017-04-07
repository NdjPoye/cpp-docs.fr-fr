---
title: "Fonctions de rappel utilisées par MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
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
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 08c6f547c95adb4c6794ec71259888d390e42e92
ms.lasthandoff: 03/06/2017

---
# <a name="callback-functions-used-by-mfc"></a>Fonctions de rappel utilisées par MFC
Trois fonctions de rappel apparaissent dans la bibliothèque Microsoft Foundation Class. Ces fonctions de rappel sont passées à [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), et [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Notez que toutes les fonctions de rappel doivent intercepter les exceptions MFC avant de retourner à Windows, étant donné que les exceptions ne peuvent pas être levées au-delà des limites de rappel. Pour plus d’informations sur les exceptions, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  

|Nom||  
|----------|-----------------|  
|[Fonction de rappel pour CDC::EnumObjects](#enum_objects)||  
|[Fonction de rappel pour CDC::GrayString](#graystring)||
|[Fonction de rappel pour CDC::SetAbortProc](#setabortproc)|| 

## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h 

## <a name="enum_objects"></a>Fonction de rappel pour CDC::EnumObjects
Le *ObjectFunc* nom est un espace réservé pour le nom de fonction fourni par l’application.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszLogObject*  
 Pointe vers une [LOGPEN](../../mfc/reference/logpen-structure.md) ou [LOGBRUSH](../../mfc/reference/logbrush-structure.md) structure de données qui contient des informations sur les attributs logiques de l’objet.  
  
 `lpData`  
 Les points de données fourni par l’application passé à la `EnumObjects` (fonction).  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction de rappel renvoie un `int`. La valeur de ce retour est définie par l’utilisateur. Si la fonction de rappel renvoie la valeur 0, `EnumObjects` arrête l’énumération au début.  
  
### <a name="remarks"></a>Remarques  
 Le nom doit être exporté.  
  
## <a name="graystring"></a>Fonction de rappel pour CDC::GrayString
*OutputFunc* est un espace réservé pour le nom de la fonction de rappel fournie par l’application.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `hDC`  
 Identifie un contexte de périphérique de mémoire avec une bitmap au moins égale à la largeur et la hauteur spécifiées par `nWidth` et `nHeight` à `GrayString`.  
  
 `lpData`  
 Pointe vers la chaîne de caractères à ajouter.  
  
 `nCount`  
 Spécifie le nombre de caractères en sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de retour de la fonction de rappel doit être **TRUE** pour indiquer la réussite ; sinon, il est **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 La fonction de rappel (*OutputFunc*) doit dessiner une image par rapport aux coordonnées (0,0) au lieu de (*x*, *y*).  

## <a name="setabortproc"></a>Fonction de rappel pour CDC::SetAbortProc
Le nom *AbortFunc* est un espace réservé pour le nom de fonction fourni par l’application.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPr*  
 Identifie le contexte de périphérique.  
  
 `code`  
 Spécifie si une erreur s’est produite. Il est 0 si aucune erreur ne se n’est produite. Il est **SP_OUTOFDISK** si le Gestionnaire d’impression n’est pas l’espace disque et davantage d’espace disque devient disponible si l’application attend. Si `code` est **SP_OUTOFDISK**, l’application ne doit pas abandonner le travail d’impression. Si elle n’est pas le cas, il doit être cédée le Gestionnaire d’impression en appelant le **PeekMessage** ou **GetMessage** fonction Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour de la fonction de gestionnaire d’abandon est différent de zéro si le travail d’impression doit continuer et 0 si elle est annulée.  
  
### <a name="remarks"></a>Notes  
 Le nom doit être exporté comme décrit dans la section Notes de [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](structures-styles-callbacks-and-message-maps.md)
 [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)
 [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)
 [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)



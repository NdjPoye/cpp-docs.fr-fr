---
title: Classe de CDockState | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
dev_langs:
- C++
helpviewer_keywords:
- dock state
- size
- docking control bars
- CDockState class
- states, dockable control bar
- position, control bar
- size, control bar
- docking tool windows
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc8beb80cc35c1816fbc305ece2bfbc5df2e7cd0
ms.lasthandoff: 02/24/2017

---
# <a name="cdockstate-class"></a>CDockState (classe)
Classe `CObject` sérialisée qui charge, décharge ou désactive l'état d'une ou de plusieurs barres de contrôles d'ancrage en mémoire persistante (un fichier).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Efface les informations sur l’état d’ancrage.|  
|[CDockState::GetVersion](#getversion)|Récupère le numéro de version de stocké barre d’état.|  
|[CDockState::LoadState](#loadstate)|Récupère des informations à partir du Registre d’état ou. Fichier INI.|  
|[CDockState::SaveState](#savestate)|Enregistre les informations d’état dans le Registre ou le fichier INI.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Tableau de pointeurs vers les données stockées ancrer les informations d’état avec une entrée pour chaque barre de contrôle.|  
  
## <a name="remarks"></a>Remarques  
 L’état d’ancrage inclut la taille et la position de la barre et si elle est ancrée. Lorsque la récupération stocké ancrer état, `CDockState` recherche de la barre de position et, si la barre n’est pas visible avec les paramètres actuels de l’écran, `CDockState` met à l’échelle de la barre de position afin qu’il soit visible. L’objectif principal de `CDockState` consiste à conserver l’état complet d’un nombre de barres de contrôles et à autoriser cet état doit être enregistré et chargé dans du Registre, l’application. Fichier INI, ou sous forme binaire dans le cadre d’un `CArchive` du contenu d’objet.  
  
 La barre peut être n’importe quel contrôle ancrable barres, y compris une barre d’outils, la barre d’état ou la barre de boîte de dialogue. `CDockState`les objets sont écrites et lues vers ou à partir d’un fichier via un `CArchive` objet.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) récupère les informations d’état de toutes les images de la fenêtre `CControlBar` les objets et les place dans le `CDockState` objet. Vous pouvez ensuite écrire le contenu de la `CDockState` objet dans le stockage avec [Serialize](../../mfc/reference/cobject-class.md#serialize) ou [CDockState::SaveState](#savestate). Si vous souhaitez ultérieurement restaurer l’état des barres de contrôles dans la fenêtre frame, vous pouvez charger l’état avec `Serialize` ou [CDockState::LoadState](#loadstate), puis utilisez [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) pour appliquer l’état enregistré à barres de contrôles de la fenêtre frame.  
  
 Pour plus d’informations sur l’ancrage des barres de contrôles, consultez les articles [les barres de contrôle](../../mfc/control-bars.md), [barres d’outils : ancrées et flottantes](../../mfc/docking-and-floating-toolbars.md), et [fenêtres Frame](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxadv.h  
  
##  <a name="a-namecleara--cdockstateclear"></a><a name="clear"></a>CDockState::Clear  
 Appelez cette fonction pour effacer toutes les informations d’ancrage dans le `CDockState` objet.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Notes  
 Cela inclut non seulement si la barre est ancrée ou non, mais la taille et la position de la barre et qu’elle soit visible ou non.  
  
##  <a name="a-namegetversiona--cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion  
 Appelez cette fonction pour récupérer le numéro de version de stocké barre d’état.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Valeur de retour  
 1 si la barre stockée des informations sont plus anciennes qu’actuelle de la barre d’état ; 2 si la barre stockée des informations sont le même que l’actuel barre d’état.  
  
### <a name="remarks"></a>Remarques  
 Prise en charge de la version permet une barre révisée ajouter de nouvelles propriétés persistantes et toujours être en mesure de détecter et de charger l’état persistant créé par une version précédente de la barre.  
  
##  <a name="a-nameloadstatea--cdockstateloadstate"></a><a name="loadstate"></a>CDockState::LoadState  
 Appelez cette fonction pour récupérer les informations d’état à partir du Registre ou. Fichier INI.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszProfileName`  
 Pointe vers une chaîne null-teminated qui spécifie le nom d’une section dans le fichier d’initialisation ou une clé dans le Registre Windows où sont stockées les informations d’état.  
  
### <a name="remarks"></a>Remarques  
 Le nom du profil est la section de l’application. Fichier INI ou du Registre qui contient des informations sur l’état des barres. Vous pouvez enregistrer le contrôle barre d’informations d’état dans le Registre ou. Fichier INI avec `SaveState`.  
  
##  <a name="a-namemarrbarinfoa--cdockstatemarrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 A `CPtrArray` objet est un tableau de pointeurs vers les informations de barre de contrôle stockée pour chaque barre de contrôle qui a enregistré les informations d’état dans le `CDockState` objet.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="a-namesavestatea--cdockstatesavestate"></a><a name="savestate"></a>CDockState::SaveState  
 Appelez cette fonction pour enregistrer les informations d’état dans le Registre ou. Fichier INI.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszProfileName`  
 Pointe vers une chaîne null-teminated qui spécifie le nom d’une section dans le fichier d’initialisation ou une clé dans le Registre Windows où sont stockées les informations d’état.  
  
### <a name="remarks"></a>Notes  
 Le nom du profil est la section de l’application. Fichier INI ou du Registre qui contient les informations d’état de la barre de contrôle. `SaveState`enregistre également la taille de l’écran actuel. Vous pouvez récupérer des informations de barre de contrôle à partir du Registre ou. Fichier INI avec `LoadState`.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)



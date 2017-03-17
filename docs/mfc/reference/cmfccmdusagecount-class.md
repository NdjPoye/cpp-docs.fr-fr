---
title: Classe de CMFCCmdUsageCount | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount class
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
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
ms.openlocfilehash: b264448af4041139018b181e2255988555267b89
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount (classe)
Effectue le suivi des messages Windows, tels que lorsque l’utilisateur sélectionne un élément dans un menu, le décompte d’utilisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Constructeur par défaut.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Incrémente d’une unité le compteur associé à la commande donnée.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Récupère le décompte d’utilisation qui est associé à l’ID de commande donné.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Détermine si cet objet a recueillies à la quantité minimale de données de suivi.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Détermine si la commande donnée est fréquemment utilisée.|  
|[CMFCCmdUsageCount::Reset](#reset)|Efface le décompte d’utilisation de toutes les commandes.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Lit de cet objet dans une archive ou écrit dans une archive. (Substitue [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Définit les valeurs de partagées `CMFCCmdUsageCount` données membres de classe.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`m_CmdUsage`|Un `CMap` objet qui mappe des commandes à leur nombre d’utilisations.|  
|`m_nMinUsagePercentage`|Le pourcentage minimal d’utilisation pour être fréquemment utilisées d’une commande.|  
|`m_nStartCount`|Le compteur de démarrage qui est utilisé pour déterminer si cet objet a recueillies à la quantité minimale de données de suivi.|  
|`m_nTotalUsage`|Le nombre de commandes de tous les suivis.|  
  
### <a name="remarks"></a>Notes  
 La `CMFCCmdUsageCount` classe mappe chaque identificateur de message Windows numérique à un compteur de l’entier non signé 32 bits. `CMFCToolBar`utilise cette classe pour afficher les éléments fréquemment utilisés. Pour plus d’informations sur `CMFCToolBar`, consultez [CMFCToolBar classe](../../mfc/reference/cmfctoolbar-class.md).  
  
 Vous pouvez conserver `CMFCCmdUsageCount` classe les données entre les exécutions de votre programme. Utilisez le [CMFCCmdUsageCount::Serialize](#serialize) méthode pour sérialiser les données membres de classe et le [CMFCCmdUsageCount::SetOptions](#setoptions) pour définir les données de membre partagé.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>CMFCCmdUsageCount::AddCmd  
 Incrémente d’une unité le compteur associé à la commande donnée.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `uiCmd`|Spécifie le compteur de commande à incrémenter.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode ajoute une nouvelle entrée à la structure du plan de comptes de la commande, de `m_CmdUsage`, si l’entrée n’existe pas déjà.  
  
 Cette méthode n’a aucun effet dans les cas suivants :  
  
-   L’infrastructure de la barre d’outils est en mode de personnalisation (les [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) méthode retourne une valeur différente de zéro).  
  
-   La commande fait référence à un séparateur de menu ou de sous-menu ( `uiCmd` est égal à 0 ou -1).  
  
- `uiCmd`fait référence à une commande standard (global `IsStandardCommand` fonction retourne une valeur différente de zéro).  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 Récupère le décompte d’utilisation qui est associé à l’ID de commande donné.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `uiCmd`|L’ID du compteur de commande à récupérer.|  
  
### <a name="return-value"></a>Valeur de retour  
 Le décompte d’utilisation qui est associé à l’ID de commande donné.  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 Détermine si cet objet a reçu la quantité minimale de données de suivi.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si cet objet a reçu la quantité minimale de suivi des données ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne une valeur différente de zéro si le nombre total, `m_nTotalUsage`, suivies de toutes les commandes est égale ou supérieure au nombre initial, `m_nStartCount`. Par défaut, le framework définit la valeur initiale 0. Vous pouvez remplacer cette valeur en utilisant la [CMFCCmdUsageCount::SetOptions](#setoptions) (méthode).  
  
 Cette méthode est utilisée par [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) pour déterminer s’il faut afficher toutes les commandes de menu disponibles.  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Détermine si la commande donnée est fréquemment utilisée.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `uiCmd`|Spécifie la commande à vérifier.|  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la commande est fréquemment utilisée ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne 0 si l’utilisation de la commande total, `m_nTotalUsage`, est égal à 0. Sinon, cette méthode retourne zéro si le pourcentage qui est utilisée la commande spécifiée est supérieur au pourcentage minimal, `m_nMinUsagePercentage`. Par défaut, l’infrastructure définit le pourcentage minimal à 5. Vous pouvez remplacer cette valeur en utilisant la [CMFCCmdUsageCount::SetOptions](#setoptions) (méthode). Si le pourcentage minimal est 0, cette méthode retourne zéro si le nombre de commandes spécifiée est supérieur à 0.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) utilise cette méthode pour déterminer si une commande est rarement utilisée.  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 Efface le décompte d’utilisation de toutes les commandes.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour effacer toutes les entrées de la structure du plan du nombre de commandes, `m_CmdUsage`et de réinitialiser l’utilisation de la commande total, `m_nTotalUsage`, compteur à 0.  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 Lit de cet objet à partir d’une archive, ou écrit dans une archive.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `ar`|Un `CArchive` objet à sérialiser depuis ou vers.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode sérialise la structure du plan du nombre de commandes, `m_CmdUsage`et l’utilisation de la commande total, `m_nTotalUsage`, compteur depuis ou vers l’archive spécifiée.  
  
 Pour des exemples de sérialisation, consultez [sérialisation : sérialisation d’un objet](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>CMFCCmdUsageCount::SetOptions  
 Définit les valeurs de partagées `CMFCCmdUsageCount` données membres de classe.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `nStartCount`|Le nouveau nombre initial de toutes les commandes.|  
|[in] `nMinUsagePercentage`|Le nouveau pourcentage minimal d’utilisation.|  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la méthode réussit, `FALSE` si le `nMinUsagePercentage` paramètre est supérieur ou égal à 100.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode définit le partage `CMFCCmdUsageCount` données membres de classe `m_nStartCount` et `m_nMinUsagePercentage` à `nStartCount` et `nMinUsagePercentage`, respectivement. `m_nStartCount`est utilisé par le [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) méthode pour déterminer si cet objet a recueillies à la quantité minimale de données de suivi. `m_nMinUsagePercentage`est utilisé par le [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) méthode pour déterminer si une commande donnée est fréquemment utilisée.  
  
 Dans les versions Debug cette méthode génère un échec d’assertion si le `nMinUsagePercentage` paramètre est supérieur ou égal à 100.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)


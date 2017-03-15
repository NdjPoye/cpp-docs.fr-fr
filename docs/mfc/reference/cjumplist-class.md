---
title: Classe de CJumpList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxadv/CJumpList
- CJumpList
dev_langs:
- C++
helpviewer_keywords:
- CJumpList class
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3662bd00f7c757df3a77f5920c48389bbd749fb
ms.lasthandoff: 02/24/2017

---
# <a name="cjumplist-class"></a>CJumpList (classe)
Un `CJumpList` est une liste de raccourcis qui s’affichent lorsque vous avec le bouton droit sur une icône dans la barre des tâches.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Construit un objet `CJumpList`.|  
|[CJumpList :: ~ CJumpList](#cjumplist__~cjumplist)|Détruit un objet `CJumpList`.|  
  
|Nom|Description|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Abandonne une transaction de création de liste sans le valider.|  
|[CJumpList::AddDestination](#adddestination)|Surchargé. Ajoute la destination à la liste.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Ajoute une catégorie connus à la liste.|  
|[CJumpList::AddTask](#addtask)|Surchargé. Ajoute des éléments à la catégorie de tâche canonique.|  
|[CJumpList::AddTasks](#addtasks)|Ajoute des éléments à la catégorie de tâche canonique.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Ajoute un séparateur entre les tâches.|  
|[CJumpList::ClearAll](#clearall)|Supprime toutes les tâches et les destinations qui ont été ajoutées à l’instance actuelle de `CJumpList` jusqu'à présent.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Supprime toutes les destinations qui ont été ajoutées à l’instance actuelle de `CJumpList` jusqu'à présent.|  
|[CJumpList::CommitList](#commitlist)|Termine une transaction de création de liste et valide la liste signalée dans le magasin associé (le Registre dans ce cas).|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Récupère un pointeur d’interface à la liste de destination.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Récupère le nombre maximal d’éléments, y compris les en-têtes de catégorie qui peuvent afficher dans le menu de destination de l’application appelante.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Retourne un tableau des éléments qui représentent supprimé des destinations.|  
|[CJumpList::InitializeList](#initializelist)|Commence une transaction de création de la liste.|  
|[CJumpList::SetAppID](#setappid)|Définit l’ID de modèle d’Application utilisateur pour obtenir la liste qui sera créée.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxadv.h  
  
##  <a name="a-namedtorcjumplista--cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>CJumpList :: ~ CJumpList  
 Détruit un objet `CJumpList`.  
  
```  
~CJumpList();
```  
  
##  <a name="a-nameabortlista--cjumplistabortlist"></a><a name="abortlist"></a>CJumpList::AbortList  
 Abandonne une transaction de création de liste sans le valider.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Remarques  
 L’appel à cette méthode a le même effet que la destruction `CJumpList` sans appeler `CommitList`.  
  
##  <a name="a-nameadddestinationa--cjumplistadddestination"></a><a name="adddestination"></a>CJumpList::AddDestination  
 Ajoute la destination à la liste.  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpcszCategoryName`  
 Spécifie un nom de catégorie. Si la catégorie spécifiée n’existe pas, il sera créé.  
  
 `strDestinationPath`  
 Spécifie un chemin d’accès au fichier de destination.  
  
 `strCategoryName`  
 Spécifie un nom de catégorie. Si la catégorie spécifiée n’existe pas, il sera créé.  
  
 `pShellItem`  
 Spécifie un élément de Shell qui représente la destination ajoutée.  
  
 `pShellLink`  
 Spécifie un lien du Shell qui représente la destination ajoutée.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 L’instance de `CJumpList` cumule en interne les destinations ajoutées, puis valide les modifications dans `CommitList`.  
  
##  <a name="a-nameaddknowncategorya--cjumplistaddknowncategory"></a><a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 Ajoute une catégorie connus à la liste.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Paramètres  
 `category`  
 Spécifie un type de catégorie connus. Peut être `KDC_RECENT`, ou `KDC_KNOWN`.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 Connu de catégories sont les catégories fréquent et récent qui nous permettra de calculer automatiquement pour chaque application qui utilise `SHAddToRecentDocs` (ou indirectement l’utilise comme l’interpréteur de commandes appellera sur le nom de l’application dans certains scénarios).  
  
##  <a name="a-nameaddtaska--cjumplistaddtask"></a><a name="addtask"></a>CJumpList::AddTask  
 Ajoute des éléments à la catégorie de tâche canonique.  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Paramètres  
 `strTargetExecutablePath`  
 Spécifie le chemin d’accès cible.  
  
 `strCommandLineArgs`  
 Spécifie les arguments de ligne de commande du fichier exécutable spécifié par strTargetExecutablePath.  
  
 `strTitle`  
 Nom de la tâche qui sera affiché dans la liste de Destination.  
  
 `strIconLocation`  
 Emplacement de l’icône qui s’affichera dans la liste de Destination ainsi que le titre.  
  
 `iIconIndex`  
 Index de l’icône.  
  
 `pShellLink`  
 Lien du shell qui représente une tâche à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 L’instance de `CJumpList` accumule les tâches spécifiées et les ajoute à la liste de Destination au cours de `CommitList`. Éléments de tâche seront affiche dans une catégorie en bas du menu de l’application de destination. Cette catégorie est prioritaire sur toutes les autres catégories lorsqu’elle est remplie dans l’interface utilisateur.  
  
##  <a name="a-nameaddtasksa--cjumplistaddtasks"></a><a name="addtasks"></a>CJumpList::AddTasks  
 Ajoute des éléments à la catégorie de tâche canonique.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Paramètres  
 `pObjectCollection`  
 Une collection de tâches à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 L’instance de CJumpList accumule les tâches spécifiées et les ajoute à la liste de Destination au cours de `CommitList`. Éléments de tâche seront affiche dans une catégorie en bas du menu de l’application de destination. Cette catégorie est prioritaire sur toutes les autres catégories lorsqu’elle est remplie dans l’interface utilisateur.  
  
##  <a name="a-nameaddtaskseparatora--cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 Ajoute un séparateur entre les tâches.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi, 0 si elle n’est pas.  
  
##  <a name="a-namecjumplista--cjumplistcjumplist"></a><a name="cjumplist"></a>CJumpList::CJumpList  
 Construit un objet `CJumpList`.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bAutoCommit`  
 Si ce paramètre a la valeur FALSE la liste n’est pas automatiquement validée dans le destructeur.  
  
##  <a name="a-nameclearalla--cjumplistclearall"></a><a name="clearall"></a>CJumpList::ClearAll  
 Supprime toutes les tâches et les destinations qui ont été ajoutées à l’instance actuelle de `CJumpList` jusqu'à présent.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode efface et libère toutes les données et les interfaces internes.  
  
##  <a name="a-nameclearalldestinationsa--cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 Supprime toutes les destinations qui ont été ajoutées à l’instance actuelle de CJumpList jusqu'à présent.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction si vous devez supprimer toutes les destinations qui ont été ajoutées jusqu'à présent dans la session en cours de création de liste de destination et l’ajouter à nouveau les autres destinations. Si le texte interne `ICustomDestinationList` a été initialisé, il est laissé actif.  
  
##  <a name="a-namecommitlista--cjumplistcommitlist"></a><a name="commitlist"></a>CJumpList::CommitList  
 Termine une transaction de création de liste et valide la liste signalée dans le magasin associé (le Registre dans ce cas).  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
 La validation est atomique. Une erreur est renvoyée si la validation échoue.  Lorsque `CommitList` est appelée, en cours est nettoyée liste d’éléments supprimés. Cette méthode de réinitialise l’objet afin qu’il n’a pas une transaction active de la construction de la liste. Pour mettre à jour la liste, `BeginList` doit être appelée à nouveau.  
  
##  <a name="a-namegetdestinationlista--cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 Récupère un pointeur d’interface à la liste de destination.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 Si la liste de liens n’a pas été initialisée, ou a été validée ou annulée, la valeur renvoyée sera `NULL`.  
  
##  <a name="a-namegetmaxslotsa--cjumplistgetmaxslots"></a><a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 Récupère le nombre maximal d’éléments, y compris les en-têtes de catégorie qui peuvent afficher dans le menu de destination de l’application appelante.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 Les applications peuvent signaler seulement un nombre d’éléments et les en-têtes de catégorie combinées jusqu'à cette valeur. Si les appels à `AppendCategory`, `AppendKnownCategory`, ou `AddUserTasks` dépasse ce nombre, ils renvoient une erreur.  
  
##  <a name="a-namegetremoveditemsa--cjumplistgetremoveditems"></a><a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 Retourne un tableau des éléments qui représentent supprimé des destinations.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 Les destinations supprimées sont récupérées lors de l’initialisation de la liste de liens. Lorsque vous générez une nouvelle liste de destination, les applications doivent traiter tout d’abord la liste de destinations supprimé, effacer les données de suivi pour tout élément retourné par l’énumérateur de la liste supprimée. Si une application tente de fournir un élément qui vient d’être supprimé dans la transaction en cours l’appel à `BeginList` démarré, l’appel de méthode qui ajouter à nouveau cet élément échoue, pour vous assurer que les applications sont en respectant la liste supprimée.  
  
##  <a name="a-nameinitializelista--cjumplistinitializelist"></a><a name="initializelist"></a>CJumpList::InitializeList  
 Commence une transaction de création de la liste.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
 Vous n’avez pas besoin d’appeler cette méthode explicitement, sauf si vous souhaitez récupérer un pointeur vers `ICustomDestinationList` à l’aide de `GetDestinationList`, le nombre d’emplacements disponibles à l’aide de `GetMaxSlots`, ou une liste d’éléments supprimés à l’aide de `GetRemovedItems`.  
  
##  <a name="a-namesetappida--cjumplistsetappid"></a><a name="setappid"></a>CJumpList::SetAppID  
 Définit l’ID de modèle d’Application utilisateur pour obtenir la liste qui sera créée.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Paramètres  
 `strAppID`  
 Chaîne qui spécifie l’ID de modèle d’Application utilisateur.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)


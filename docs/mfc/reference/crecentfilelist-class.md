---
title: Classe de CRecentFileList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- files [C++], most recently used
- MRU files
- CRecentFileList class
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5d18daee2e4d809c750ae4654d731888df1db39e
ms.lasthandoff: 02/24/2017

---
# <a name="crecentfilelist-class"></a>CRecentFileList (classe)
Prend en charge le contrôle de la liste des derniers fichiers utilisés (MRU).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Construit un objet `CRecentFileList`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Ajoute un fichier à la liste des derniers fichiers utilisés.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Fournit un nom d’affichage pour l’affichage de menu d’un nom de fichier des derniers fichiers utilisés.|  
|[CRecentFileList::GetSize](#getsize)|Récupère le nombre de fichiers dans la liste des derniers fichiers utilisés.|  
|[CRecentFileList::ReadList](#readlist)|Lit la liste des fichiers des derniers fichiers utilisés dans le Registre ou. Fichier INI.|  
|[CRecentFileList::Remove](#remove)|Supprime un fichier dans la liste des derniers fichiers utilisés.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Met à jour l’affichage du menu de la liste des fichiers des derniers fichiers utilisés.|  
|[CRecentFileList::WriteList](#writelist)|Écrit la dernière liste de fichiers à partir du Registre ou. Fichier INI.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[[] CRecentFileList::operator](#operator_at)|Retourne un `CString` objet à une position donnée.|  
  
## <a name="remarks"></a>Remarques  
 Fichiers peuvent être ajoutés ou supprimés dans la liste des derniers fichiers utilisés, la liste des fichiers permettre être lues ou écrite dans le Registre ou un. Ini et le menu Affichage de la liste des fichiers MRU peuvent être mis à jour.  
  
 Pour plus d’informations sur les éléments de menu des derniers fichiers utilisés, consultez  
  
-   L’article de la Base de connaissances Q243751 : comment faire : ajouter des gestionnaires de commandes pour les éléments de Menu des derniers fichiers utilisés dans une Application MFC  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CRecentFileList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxadv.h  
  
##  <a name="add"></a>CRecentFileList::Add  
 Ajoute un fichier à la liste des fichiers récemment utilisée (MRU).  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Spécifie le chemin d’accès à ajouter à la liste.  
  
 `lpszAppID`  
 Spécifie l’ID de modèle d’Application utilisateur pour l’application.  
  
 `pItem`  
 Spécifie un pointeur vers un élément d’interface à ajouter à la liste.  
  
 `pLink`  
 Spécifie un pointeur vers le lien du Shell à ajouter à la liste.  
  
 `pidl`  
 Spécifie le conjointe pour l’élément d’interface qui doit être ajouté au dossier documents récents.  
  
### <a name="remarks"></a>Notes  
 Le nom de fichier est ajouté en haut de la liste des derniers fichiers utilisés. Si le nom de fichier existe déjà dans la liste des derniers fichiers utilisés, il sera déplacé vers le haut.  
  
##  <a name="crecentfilelist"></a>CRecentFileList::CRecentFileList  
 Construit un objet `CRecentFileList`.  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStart`  
 Décalage de la numérotation dans l’affichage du menu de la liste des fichiers MRU (utilisé le plus récemment).  
  
 `lpszSection`  
 Pointe vers le nom de la section du Registre ou l’application. Fichier INI dans lequel la liste des fichiers MRU est lu et/ou écrite.  
  
 `lpszEntryFormat`  
 Pointe vers une chaîne de format à utiliser pour les noms des entrées stockées dans le Registre ou l’application. Fichier INI.  
  
 `nSize`  
 Nombre maximal de fichiers dans la liste des derniers fichiers utilisés.  
  
 `nMaxDispLen`  
 Longueur maximale, en caractères, disponibles pour l’affichage du menu d’un nom de fichier dans la liste des derniers fichiers utilisés.  
  
### <a name="remarks"></a>Remarques  
 La chaîne de format vers lequel pointe `lpszEntryFormat` doit contenir « %d », qui sera utilisé pour la substitution de l’index de chaque élément des derniers fichiers utilisés. Par exemple, si la chaîne de format est `"file%d"` alors les entrées seront nommées `file0`, `file1`, et ainsi de suite.  
  
##  <a name="getdisplayname"></a>CRecentFileList::GetDisplayName  
 Obtient un nom d’affichage d’un fichier dans la liste des fichiers MRU, pour une utilisation dans l’affichage du menu de la liste des derniers fichiers utilisés.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `strName`  
 Chemin d’accès complet du fichier dont le nom doit être affiché dans la liste de menus de fichiers MRU.  
  
 `nIndex`  
 Index de base zéro du fichier dans la liste des derniers fichiers utilisés.  
  
 *lpszCurDir*  
 Chaîne contenant le répertoire actif.  
  
 *nCurDir*  
 Longueur de la chaîne du répertoire en cours.  
  
 `bAtLeastName`  
 Si différent de zéro, indique que le nom du fichier de base doit être retourné, même si elle dépasse la longueur maximale d’affichage (passée comme le `nMaxDispLen` paramètre à la `CRecentFileList` constructeur).  
  
### <a name="return-value"></a>Valeur de retour  
 **FALSE** si il n’existe aucun nom de fichier à l’index spécifié dans la liste des fichiers récemment utilisée (MRU).  
  
### <a name="remarks"></a>Remarques  
 Si le fichier se trouve dans le répertoire en cours, la fonction quitte le répertoire désactive l’affichage. Si le nom de fichier est trop long, le répertoire et l’extension sont supprimés. Si le nom de fichier est toujours trop long, le nom d’affichage est défini sur une chaîne vide, sauf si `bAtLeastName` est différente de zéro.  
  
##  <a name="getsize"></a>CRecentFileList::GetSize  
 Récupère le nombre de fichiers dans la liste des derniers fichiers utilisés.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de fichiers en cours utilisé récemment la liste (MRU).  
  
##  <a name="operator_at"></a>[] CRecentFileList::operator  
 L’indice surchargé ( `[]`) opérateur retourne une seule `CString` spécifié par l’index de base zéro dans `nIndex`.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro d’un `CString` dans un ensemble de `CString`s.  
  
##  <a name="readlist"></a>CRecentFileList::ReadList  
 Lit le plus récemment utilisé la liste (MRU) à partir du Registre ou l’application. Fichier INI.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>CRecentFileList::Remove  
 Supprime un fichier dans la liste des derniers fichiers utilisés.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du fichier à supprimer de la liste des fichiers récemment utilisée (MRU).  
  
##  <a name="updatemenu"></a>CRecentFileList::UpdateMenu  
 Met à jour l’affichage du menu de la liste des fichiers des derniers fichiers utilisés.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers le [CCmdUI](../../mfc/reference/ccmdui-class.md) objet pour le menu de liste des derniers fichiers utilisé (MRU) fichier.  
  
##  <a name="writelist"></a>CRecentFileList::WriteList  
 Écrit le plus récemment (MRU) liste des fichiers utilisés dans le Registre ou l’application. Fichier INI.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)





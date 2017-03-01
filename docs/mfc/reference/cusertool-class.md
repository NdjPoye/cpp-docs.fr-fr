---
title: Classe de CUserTool | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserTool
dev_langs:
- C++
helpviewer_keywords:
- CUserTool class
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
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
ms.openlocfilehash: 2e0b082be6aac7314d8251f89b42ed09e44e2f3d
ms.lasthandoff: 02/24/2017

---
# <a name="cusertool-class"></a>CUserTool (classe)
Un outil utilisateur est un élément de menu qui exécute une application externe. Le **outils** onglet de la **personnaliser** boîte de dialogue ( [CMFCToolBarsCustomizeDialog classe](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) permet à l’utilisateur d’ajouter des outils utilisateur et pour spécifier le nom de commande, arguments et répertoire initial de chaque outil utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Dessine l’icône utilisateur dans un rectangle spécifié.|  
|[CUserTool::GetCommand](#getcommand)|Retourne une chaîne qui contient le texte de la commande associée à l’outil.|  
|[CUserTool::GetCommandId](#getcommandid)|Retourne l’ID de commande de l’élément de menu de l’outil.|  
|[CUserTool::Invoke](#invoke)|Exécute la commande associée à l’outil.|  
|[CUserTool::Serialize](#serialize)|Lit ou écrit cet objet dans une archive. (Substitue [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Définit la commande associée à l’outil.|  
|[CUserTool::SetToolIcon](#settoolicon)|Charge l’icône de l’outil à partir de l’application associée à l’outil.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Charge l’icône par défaut pour un outil utilisateur.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Les arguments de ligne de commande pour l’outil.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Le répertoire initial de l’outil de l’utilisateur.|  
|[CUserTool::m_strLabel](#m_strlabel)|Le nom de l’outil qui s’affiche dans l’élément de menu de l’outil.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur la façon d’activer les outils utilisateur dans votre application, consultez la page [CUserToolsManager classe](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment créer un outil d’un `CUserToolsManager` de l’objet, définissez les `m_strLabel` variable de membre et définir l’application qui exécute l’outil. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#35;](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxusertool.h  
  
##  <a name="a-namecopyicontoclipboarda--cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedrawtoolicona--cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon  
 Dessine l’icône de l’outil dans le centre d’un rectangle spécifié.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rectImage`  
 Spécifie les coordonnées de la zone pour afficher l’icône.  
  
##  <a name="a-namegetcommanda--cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::GetCommand  
 Retourne une chaîne qui contient le texte de la commande associée à l’outil.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à `CString` objet qui contient le texte de la commande associée à l’outil.  
  
##  <a name="a-namegetcommandida--cusertoolgetcommandid"></a><a name="getcommandid"></a>CUserTool::GetCommandId  
 Retourne l’ID de commande de l’outil.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de cet outil utilisateur.  
  
##  <a name="a-nameinvokea--cusertoolinvoke"></a><a name="invoke"></a>CUserTool::Invoke  
 Exécute la commande associée à l’outil.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la commande a été exécutée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Appels [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) pour exécuter une commande associée à l’outil. La fonction échoue si la commande est vide ou si [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) échoue.  
  
##  <a name="a-nameloaddefaulticona--cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUserTool::LoadDefaultIcon  
 Charge l’icône par défaut pour un outil utilisateur.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle de l’icône chargé ( `HICON`), ou `NULL` si l’icône par défaut ne peut pas être chargé.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette méthode lorsqu’il est impossible de charger une icône pour un outil défini par l’utilisateur à partir du fichier exécutable de l’outil.  
  
 Substituez cette méthode pour fournir votre propre icône par défaut de l’outil.  
  
##  <a name="a-namemstrargumentsa--cusertoolmstrarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments  
 Les arguments de ligne de commande pour l’outil.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette chaîne est passée à l’outil lorsque vous appelez [CUserTool::Invoke](#invoke) ou lorsqu’un utilisateur clique sur la commande associée à cet outil.  
  
##  <a name="a-namemstrinitialdirectorya--cusertoolmstrinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory  
 Spécifie le répertoire initial de l’outil de l’utilisateur.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette variable Spécifie le répertoire initial, l’outil s’exécute dans lorsque vous appelez [CUserTool::Invoke](#invoke) ou lorsqu’un utilisateur clique sur la commande associée à cet outil.  
  
##  <a name="a-namemstrlabela--cusertoolmstrlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel  
 L’étiquette est affichée dans l’élément de menu de l’outil.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="a-nameserializea--cusertoolserialize"></a><a name="serialize"></a>CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ar`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetcommanda--cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::SetCommand  
 Définit l’application qui exécute l’outil.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszCmd`  
 Spécifie la nouvelle application à associer à l’outil.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour définir une nouvelle application qui exécute l’outil. La méthode détruit l’icône ancien et charge une nouvelle icône de l’application donnée. Si elle ne peut pas charger une icône de l’application, il charge l’icône par défaut pour un outil utilisateur en appelant [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="a-namesettoolicona--cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::SetToolIcon  
 Charge l’icône de l’outil à partir de l’application qui utilise l’outil.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle de l’icône chargé.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour charger l’icône à afficher sur l’élément de menu. Cette méthode recherche l’icône dans le fichier exécutable qui utilise l’outil. Si elle ne dispose pas d’une icône par défaut, l’icône fournie par [CUserTool::LoadDefaultIcon](#loaddefaulticon) est utilisé à la place.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager (classe)](../../mfc/reference/cusertoolsmanager-class.md)


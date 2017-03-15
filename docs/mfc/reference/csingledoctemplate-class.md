---
title: Classe CSingleDocTemplate | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- templates, SDI
- document templates, single
- single document interface (SDI), applications
- CSingleDocTemplate class
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 78e288dd958e73495a8d513d7fe3427ccc956a61
ms.lasthandoff: 02/24/2017

---
# <a name="csingledoctemplate-class"></a>Classe CSingleDocTemplate
Définit un modèle de document qui implémente l'interface monodocument (SDI).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Construit un objet `CSingleDocTemplate`.|  
  
## <a name="remarks"></a>Remarques  
 Une application SDI utilise la fenêtre frame principale pour afficher un document ; un seul document peut être ouvert à la fois.  
  
 Un modèle de document définit la relation entre les trois types de classes :  
  
-   Une classe de document, vous dérivez de **CDocument**.  
  
-   Une classe d’affichage, qui affiche des données à partir de la classe de document répertoriée ci-dessus. Vous pouvez dériver de cette classe à partir de `CView`, `CScrollView`, `CFormView`, ou `CEditView`. (Vous pouvez également utiliser `CEditView` directement.)  
  
-   Une classe de fenêtre frame, qui contient la vue. Pour un modèle de document SDI, vous pouvez dériver de cette classe à partir de `CFrameWnd`des fenêtres frame ; s’il est inutile de personnaliser le comportement de la main, vous pouvez utiliser `CFrameWnd` directement sans dériver votre propre classe.  
  
 Une application SDI généralement prend en charge un type de document, afin qu’il a un seul `CSingleDocTemplate` objet. Un seul document peut être ouvert à la fois.  
  
 Vous n’avez pas besoin d’appeler des fonctions de n’importe quel membre `CSingleDocTemplate` sauf le constructeur. Les poignées de framework `CSingleDocTemplate` objets en interne.  
  
 Pour plus d’informations sur l’utilisation de `CSingleDocTemplate`, consultez [modèles de Document et le processus de création de Document/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-namecsingledoctemplatea--csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a>CSingleDocTemplate::CSingleDocTemplate  
 Construit un objet `CSingleDocTemplate`.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDResource`  
 Spécifie l’ID des ressources utilisées avec le type de document. Cela peut inclure le menu, icône, table d’accélérateurs et des ressources de chaîne.  
  
 La ressource de chaîne se compose d’au moins sept sous-chaînes séparés par le caractère « \n » (le caractère '\n' est requis, car un espace réservé si une sous-chaîne n’est pas incluse ; Toutefois, les caractères de fin '\n' ne sont pas nécessaires) ; Ces sous-chaînes décrivent le type de document. Pour plus d’informations sur les sous-chaînes, consultez [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Cette ressource de chaîne se trouve dans le fichier de ressources. Exemple :  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 Vous pouvez modifier cette chaîne à l’aide de l’éditeur de chaînes ; la chaîne entière apparaît comme une seule entrée dans l’éditeur de chaînes, pas comme les sept entrées différentes.  
  
 Pour plus d’informations sur ces types de ressources, consultez le [éditeur de chaînes](../../windows/string-editor.md).  
  
 `pDocClass`  
 Pointe vers le `CRuntimeClass` objet de la classe de document. Cette classe est un **CDocument**-vous définissez pour représenter vos documents de classe dérivée.  
  
 `pFrameClass`  
 Pointe vers le `CRuntimeClass` objet de la classe de fenêtre frame. Cette classe peut être un `CFrameWnd`-classe dérivée, ou il peut être `CFrameWnd` elle-même si vous préférez le comportement par défaut pour votre fenêtre frame principale.  
  
 `pViewClass`  
 Pointe vers le `CRuntimeClass` objet de la classe d’affichage. Cette classe est un `CView`-vous définissez pour afficher vos documents de classe dérivée.  
  
### <a name="remarks"></a>Remarques  
 Allouer dynamiquement un `CSingleDocTemplate` de l’objet et le passer à `CWinApp::AddDocTemplate` à partir de la `InitInstance` fonction membre de classe de votre application.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocViewSDI&#13;](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI&#14;](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument (classe)](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate (classe)](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)   
 [CWinApp (classe)](../../mfc/reference/cwinapp-class.md)


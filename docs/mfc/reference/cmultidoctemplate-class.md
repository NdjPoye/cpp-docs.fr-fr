---
title: Classe de CMultiDocTemplate | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- MDI, template
- CMultiDocTemplate class
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 6e58325cd4dcaec01bf8a76006bb397fccd9a171
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate (classe)
Définit un modèle de document qui implémente l'interface multidocument (MDI).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Construit un objet `CMultiDocTemplate`.|  
  
## <a name="remarks"></a>Remarques  
 Une application MDI utilise la fenêtre frame principale comme un espace de travail dans lequel l’utilisateur peut ouvrir des fenêtres frame de document zéro ou plus, chacun d'entre eux affiche un document. Pour obtenir une description plus détaillée de l’interface MDI, consultez *Windows Interface Guidelines for Software Design*.  
  
 Un modèle de document définit les relations entre les trois types de classes :  
  
-   Une classe de document, vous dérivez de [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Une classe d’affichage, qui affiche des données à partir de la classe de document répertoriée ci-dessus. Vous pouvez dériver de cette classe à partir de [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, ou `CEditView`. (Vous pouvez également utiliser `CEditView` directement.)  
  
-   Une classe de fenêtre frame, qui contient la vue. Pour un modèle de document MDI, vous pouvez dériver de cette classe à partir de `CMDIChildWnd`, ou, si vous n’avez pas besoin de personnaliser le comportement des fenêtres frame, vous pouvez utiliser [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) directement sans dériver votre propre classe.  
  
 Une application MDI peut prendre en charge plusieurs types de documents et des documents de types différents peuvent être ouvertes en même temps. Votre application dispose d’un modèle de document pour chaque type de document pris en charge. Par exemple, si votre application MDI prend en charge les feuilles de calcul et des documents texte, l’application possède deux `CMultiDocTemplate` objets.  
  
 L’application utilise les modèles de document lorsque l’utilisateur crée un nouveau document. Si l’application prend en charge plusieurs types de document, le framework Obtient les noms des types de documents pris en charge dans les modèles de document et les affiche dans une liste dans la boîte de dialogue Nouveau fichier. Une fois que l’utilisateur a sélectionné un type de document, l’application crée un objet de classe de document, un objet fenêtre frame et un objet de vue et attache les uns aux autres.  
  
 Vous n’avez pas besoin d’appeler des fonctions de n’importe quel membre `CMultiDocTemplate` sauf le constructeur. Les poignées de framework `CMultiDocTemplate` objets en interne.  
  
 Pour plus d’informations sur `CMultiDocTemplate`, consultez [modèles de Document et le processus de création de Document/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
 Construit un objet `CMultiDocTemplate`.  
  
```  
CMultiDocTemplate(
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
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Notez que la chaîne commence par un caractère « \n » ; Il s’agit, car la première sous-chaîne n’est pas utilisée pour les applications MDI et n’est donc pas incluse. Vous pouvez modifier cette chaîne à l’aide de l’éditeur de chaînes ; la chaîne entière apparaît comme une seule entrée dans l’éditeur de chaînes, pas comme les sept entrées différentes.  
  
 Pour plus d’informations sur ces types de ressources, consultez [éditeurs de ressources](../../windows/resource-editors.md).  
  
 `pDocClass`  
 Pointe vers le `CRuntimeClass` objet de la classe de document. Cette classe est un **CDocument**-vous définissez pour représenter vos documents de classe dérivée.  
  
 `pFrameClass`  
 Pointe vers le `CRuntimeClass` objet de la classe de fenêtre frame. Cette classe peut être un `CMDIChildWnd`-classe dérivée, ou il peut être `CMDIChildWnd` lui-même si vous souhaitez que vos fenêtres frame de document par défaut.  
  
 `pViewClass`  
 Pointe vers le `CRuntimeClass` objet de la classe d’affichage. Cette classe est un `CView`-vous définissez pour afficher vos documents de classe dérivée.  
  
### <a name="remarks"></a>Remarques  
 Allouer dynamiquement une `CMultiDocTemplate` objet pour chaque type de document que votre application prend en charge et de passer chacun d’eux au `CWinApp::AddDocTemplate` à partir de la `InitInstance` fonction membre de classe de votre application.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#92;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 Voici un autre exemple.  
  
 [!code-cpp[NVC_MFCDocView&#93;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)   
 [Classe CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp (classe)](../../mfc/reference/cwinapp-class.md)


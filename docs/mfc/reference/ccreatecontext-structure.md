---
title: Structure de CCreateContext | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 231f2e44e085d27a2b2cbf289adf7b0521471b0e
ms.lasthandoff: 02/24/2017

---
# <a name="ccreatecontext-structure"></a>Structure de CCreateContext
L’infrastructure utilise le `CCreateContext` structure lorsqu’il crée les fenêtres frames et les vues qui sont associés à un document.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Remarques  
 `CCreateContext`est une structure et ne dispose pas d’une classe de base.  
  
 Lorsque vous créez une fenêtre, les valeurs dans cette structure fournissent les informations utilisées pour connecter les composants d’un document à l’affichage de ses données. Vous devez uniquement utiliser `CCreateContext` si vous substituez les parties du processus de création.  
  
 Un `CCreateContext` structure contient des pointeurs vers le document, la fenêtre frame, la vue et le modèle de document. Il contient également un pointeur vers un `CRuntimeClass` qui identifie le type de vue à créer. Les informations de classe d’exécution et le pointeur de document en cours sont utilisés pour créer une nouvelle vue de manière dynamique. Le tableau suivant indique comment et quand chaque `CCreateContext` membre peut être utilisé :  
  
|Membre|Type|Qu’est|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`de la nouvelle vue à créer.|  
|`m_pCurrentDoc`|`CDocument*`|Le document existant à associer à la nouvelle vue.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Le modèle de document associé à la création d’une fenêtre frame MDI.|  
|`m_pLastView`|`CView*`|L’affichage d’origine sur lequel sont modélisées affichages supplémentaires, comme la création d’affichages de fenêtre de fractionnement ou de la création d’une seconde vue sur un document.|  
|`m_pCurrentFrame`|`CFrameWnd*`|La fenêtre frame sur lequel sont modélisées fenêtres frames supplémentaires, comme dans la création d’une deuxième fenêtre frame dans un document.|  
  
 Lorsqu’un modèle de document crée un document et ses composants associés, il valide les informations stockées dans le `CCreateContext` structure. Par exemple, une vue ne doit pas être créée pour un document qui n’existe pas.  
  
> [!NOTE]
>  Tous les pointeurs de `CCreateContext` sont facultatives et peuvent être `NULL` si inconnu ou non spécifié.  
  
 `CCreateContext`est utilisé par les fonctions membres répertoriées sous « Voir aussi ». Pour plus d’informations, consultez les descriptions de ces fonctions si vous envisagez de les remplacer.  
  
 Voici quelques recommandations générales :  
  
-   Lorsque passée comme argument pour la création de la fenêtre, comme dans `CWnd::Create`, `CFrameWnd::Create`, et `CFrameWnd::LoadFrame`, le contexte de création spécifie ce que la nouvelle fenêtre doit être connectée. Pour la plupart des fenêtres, la structure entière est facultative et un `NULL` pointeur peut être passé.  
  
-   Pour les fonctions membres substituables, tels que `CFrameWnd::OnCreateClient`, `CCreateContext` argument est facultatif.  
  
-   Pour les fonctions membres impliquées dans la vue Création, vous devez fournir suffisamment d’informations pour créer la vue. Par exemple, pour la première vue dans une fenêtre fractionnée, vous devez fournir les informations de classe d’affichage et le document actif.  
  
 En général, si vous utilisez les valeurs par défaut de framework, vous pouvez ignorer `CCreateContext`. Si vous essayez de modifications plus complexes, le code source de Microsoft Foundation Class Library ou les exemples de programmes, tels que VIEWEX, vous guide. Si vous oubliez d’un paramètre obligatoire, une assertion framework vous indique ce que vous avez oublié.  
  
 Pour plus d’informations sur `CCreateContext`, consultez l’exemple MFC [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create statiques](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)



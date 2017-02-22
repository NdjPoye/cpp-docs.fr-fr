---
title: "CCreateContext Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCreateContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCreateContext structure"
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CCreateContext Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'infrastructure utilise la structure d' `CCreateContext` lorsqu'il crée les fenêtres frames et les vues qui sont associées à un document.  
  
## Syntaxe  
  
```  
struct CCreateContext  
```  
  
## Notes  
 `CCreateContext` est une structure et n'a pas de classe de base.  
  
 Lorsque vous créez une fenêtre, les valeurs dans cette structure fournissent des informations utilisées pour connecter des composants d'un document à l'affichage de ses données.  Vous devez utiliser `CCreateContext` si vous substituez des parties du processus de création.  
  
 Une structure d' `CCreateContext` contient des pointeurs vers le document, à la fenêtre frame, à la vue, et au modèle de document.  Elle contient également un pointeur vers `CRuntimeClass` qui identifie le type de vue à créer.  Les informations sur la classe à l'exécution et le pointeur du document actuel sont utilisés pour créer une nouvelle vue dynamiquement.  Le tableau suivant l'indique comment et quand chaque membre d' `CCreateContext` peut être utilisé :  
  
|Membre|Type|Pour ce qu'il soit|  
|------------|----------|------------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` de la nouvelle vue à créer.|  
|`m_pCurrentDoc`|`CDocument*`|Le document existant à associer à la nouvelle vue.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Le modèle de document associé à la création d'une nouvelle fenêtre frame MDI.|  
|`m_pLastView`|`CView*`|La vue d'origine sur lequel les affichages supplémentaires sont modelées, comme dans la création des vues de fenêtre fractionnée ou la création d'une nouvelle vue d'un document.|  
|`m_pCurrentFrame`|`CFrameWnd*`|La fenêtre frame sur lequel les fenêtres frames supplémentaires sont modelées, comme lors de la création d'une deuxième fenêtre frame sur un document.|  
  
 Lorsqu'un modèle de document crée un document et ses composants associés, il valide les informations stockées dans la structure d' `CCreateContext` .  Par exemple, une vue ne doit pas être créée pour un document inexistante.  
  
> [!NOTE]
>  Tous les pointeurs dans `CCreateContext` sont facultatifs et peuvent être `NULL` si non spécifié ou inconnu.  
  
 `CCreateContext` est utilisé par les fonctions membres répertoriés sous « consultez également. » Consultez les descriptions de ces fonctions pour des informations spécifiques si vous envisagez de les remplacer.  
  
 Voici quelques recommandations générales :  
  
-   Une fois passé comme un argument pour la création de fenêtre, comme dans `CWnd::Create`, `CFrameWnd::Create`, et `CFrameWnd::LoadFrame`, le contexte de créer spécifie que la nouvelle fenêtre doit être connectée.  Pour la plupart des fenêtres, la structure entière est facultative et un pointeur d' `NULL` peut être passé.  
  
-   Pour les fonctions membres substituables, telles que `CFrameWnd::OnCreateClient`, l'argument d' `CCreateContext` est facultatif.  
  
-   Pour les fonctions membres impliqués dans la création de vue, vous devez fournir suffisamment d'informations pour créer la vue.  Par exemple, pour la première vue dans une fenêtre fractionnée, vous devez fournir les informations de classe d'affichage et le document actif.  
  
 En général si vous utilisez l'infrastructure a comme valeur par défaut, vous pouvez ignorer `CCreateContext`.  Si vous essayez les modifications plus avancées, le code source de la bibliothèque MFC ou les exemples de programme, tels que VIEWEX, vous guidera.  Si vous oubliez un paramètre requis, une assertion d'infrastructure vous indique que vous avez oublié.  
  
 Pour plus d'informations sur `CCreateContext`, consultez l'exemple [VIEWEX](../../top/visual-cpp-samples.md)MFC.  
  
## Configuration requise  
 **en\-tête :** afxext.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../Topic/CFrameWnd::Create.md)   
 [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)   
 [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)   
 [CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)   
 [CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)
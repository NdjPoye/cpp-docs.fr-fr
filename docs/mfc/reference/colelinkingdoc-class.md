---
title: "COleLinkingDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinkingDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinkingDoc class"
  - "OLE containers, client items"
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleLinkingDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour les documents de conteneur OLE qui prennent en charge la liaison aux éléments inclus ils contiennent.  
  
## Syntaxe  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](../Topic/COleLinkingDoc::COleLinkingDoc.md)|Construit un objet `COleLinkingDoc`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinkingDoc::Register](../Topic/COleLinkingDoc::Register.md)|Enregistre le document avec les DLL système OLE.|  
|[COleLinkingDoc::Revoke](../Topic/COleLinkingDoc::Revoke.md)|Révoque l'inscription du document.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](../Topic/COleLinkingDoc::OnFindEmbeddedItem.md)|Recherche l'élément incorporé spécifié.|  
|[COleLinkingDoc::OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md)|Recherche l'élément lié spécifié.|  
  
## Notes  
 Une application conteneur que la liaison prend en charge des éléments inline est appelé « conteneur de lien. » l'exemple d'application d' [OCLIENT](../../top/visual-cpp-samples.md) est un exemple d'un conteneur de lien.  
  
 Lorsque la source d'un élément lié est un élément inclus dans un autre document, ce document contenant doit être chargé pour que l'élément inline est modifié.  Pour cette raison, un conteneur de lien doit pouvoir être activé par une autre application conteneur lorsque l'utilisateur souhaite modifier la source de l'élément lié.  Votre application doit également utiliser la classe de [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) afin qu'il puisse créer des documents une fois activé par programme.  
  
 Pour rendre votre conteneur un conteneur de lien, dérivez votre classe de document d' `COleLinkingDoc` au lieu de [COleDocument](../../mfc/reference/coledocument-class.md).  Comme avec tout autre conteneur OLE, vous devez concevoir votre classe pour stocker les données natives de l'application ainsi qu'un incorporé ou des éléments liés.  De plus, vous devez concevoir des structures de données pour stocker les données natives.  Si vous définissez `CDocItem`classe dérivée pour les données natives de votre application, vous pouvez utiliser l'interface définie par `COleDocument` pour stocker les données natives ainsi que OLE vos données.  
  
 Pour permettre à votre application d'être lancé par programme par un autre conteneur, déclarez un objet d' `COleTemplateServer` en tant que membre d' `CWinApp`de votre application classe dérivée de :  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/CPP/colelinkingdoc-class_1.h)]  
  
 Dans la fonction membre d' `InitInstance` de votre `CWinApp`classe dérivée, créez un modèle de document et spécifiez votre `COleLinkingDoc`classe dérivée comme la classe de document :  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/CPP/colelinkingdoc-class_2.cpp)]  
  
 Connectez votre objet d' `COleTemplateServer` à vos modèles de document en appelant la fonction membre d' `ConnectTemplate` de l'objet, et stocker tous les objets de classe avec OLE le système en appelant **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/CPP/colelinkingdoc-class_3.cpp)]  
  
 Pour obtenir un exemple `CWinApp`\- la définition de classe dérivée et l' `InitInstance` fonctionnent, consultez OCLIENT.H et OCLIENT.CPP dans l'exemple [OCLIENT](../../top/visual-cpp-samples.md)MFC.  
  
 Pour plus d'informations sur l'utilisation `COleLinkingDoc`, consultez les articles [conteneurs : implémenter un conteneur](../../mfc/containers-implementing-a-container.md) et [conteneurs : Fonctionnalités avancées](../../mfc/containers-advanced-features.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)
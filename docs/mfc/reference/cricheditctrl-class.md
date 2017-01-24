---
title: "CRichEditCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl class"
  - "CRichEditCtrl class, contrôles communs"
  - "formatted text [C++]"
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle RichEdit.  
  
## Syntaxe  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](../Topic/CRichEditCtrl::CRichEditCtrl.md)|Construit un objet `CRichEditCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditCtrl::CanPaste](../Topic/CRichEditCtrl::CanPaste.md)|Détermine si le contenu du presse\-papiers peut être collé dans ce contrôle RichEdit.|  
|[CRichEditCtrl::CanRedo](../Topic/CRichEditCtrl::CanRedo.md)|Détermine si des actions dans la file d'attente de rétablissement du contrôle.|  
|[CRichEditCtrl::CanUndo](../Topic/CRichEditCtrl::CanUndo.md)|Détermine si une opération de modification peut être annulée.|  
|[CRichEditCtrl::CharFromPos](../Topic/CRichEditCtrl::CharFromPos.md)|Récupère des informations sur le caractère le plus proche d'un point spécifié dans la zone cliente d'un contrôle d'édition.|  
|[CRichEditCtrl::Clear](../Topic/CRichEditCtrl::Clear.md)|Efface la sélection actuelle.|  
|[CRichEditCtrl::Copy](../Topic/CRichEditCtrl::Copy.md)|Copie la sélection actuelle dans le presse\-papiers.|  
|[CRichEditCtrl::Create](../Topic/CRichEditCtrl::Create.md)|Crée le contrôle RichEdit windows et l'associe à cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::CreateEx](../Topic/CRichEditCtrl::CreateEx.md)|Crée le contrôle RichEdit windows avec les styles étendus Windows spécifiés et l'associe à cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::Cut](../Topic/CRichEditCtrl::Cut.md)|Fractionne la sélection actuelle dans le presse\-papiers.|  
|[CRichEditCtrl::DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md)|Affiche une partie du contenu de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::EmptyUndoBuffer](../Topic/CRichEditCtrl::EmptyUndoBuffer.md)|Réinitialise \(espaces inscription\) la balise d'annulation de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::FindText](../Topic/CRichEditCtrl::FindText.md)|Recherche le texte dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::FindWordBreak](../Topic/CRichEditCtrl::FindWordBreak.md)|Recherche l'arrêt du mot avant ou après la position de caractère spécifiée, ou récupère des informations sur le caractère à cette position.|  
|[CRichEditCtrl::FormatRange](../Topic/CRichEditCtrl::FormatRange.md)|Met en forme une plage de texte pour le périphérique de sortie cible.|  
|[CRichEditCtrl::GetCharPos](../Topic/CRichEditCtrl::GetCharPos.md)|Détermine l'emplacement d'un caractère donné dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md)|Récupère les attributs de mise en forme de caractère par défaut présents dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md)|Récupère le masque d'événements pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetFirstVisibleLine](../Topic/CRichEditCtrl::GetFirstVisibleLine.md)|Détermine la ligne visible le plus élevé cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetIRichEditOle](../Topic/CRichEditCtrl::GetIRichEditOle.md)|Extrait un pointeur vers l'interface d' `IRichEditOle` pour ce contrôle RichEdit.|  
|[CRichEditCtrl::GetLimitText](../Topic/CRichEditCtrl::GetLimitText.md)|Obtient la limite de la quantité de texte qu'un utilisateur peut entrer dans cet `CRichEditCtrl` l'objet.|  
|[CRichEditCtrl::GetLine](../Topic/CRichEditCtrl::GetLine.md)|Extrait une ligne de texte de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetLineCount](../Topic/CRichEditCtrl::GetLineCount.md)|Récupère le nombre de lignes de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetModify](../Topic/CRichEditCtrl::GetModify.md)|Détermine si le contenu de cet objet d' `CRichEditCtrl` a changé depuis la dernière sauvegarde.|  
|[CRichEditCtrl::GetOptions](../Topic/CRichEditCtrl::GetOptions.md)|Récupère les options de contrôle RichEdit.|  
|[CRichEditCtrl::GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md)|Récupère les attributs de mise en forme de paragraphe dans la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetPunctuation](../Topic/CRichEditCtrl::GetPunctuation.md)|Récupère les caractères de ponctuation actuels pour le contrôle RichEdit.  Ce message est uniquement disponible dans les versions linguistiques du système d'exploitation.|  
|[CRichEditCtrl::GetRect](../Topic/CRichEditCtrl::GetRect.md)|Récupère le rectangle de mise en forme pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetRedoName](../Topic/CRichEditCtrl::GetRedoName.md)|Récupère le type de l'action suivante, le cas échéant, dans la file d'attente de rétablissement du contrôle.|  
|[CRichEditCtrl::GetSel](../Topic/CRichEditCtrl::GetSel.md)|Obtient les positions de début et de fin de la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md)|Récupère les attributs de mise en forme de caractères dans la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md)|Récupère le type de contenu dans la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::GetSelText](../Topic/CRichEditCtrl::GetSelText.md)|Obtient le texte de la sélection actuelle dans cet objet d' `CRichEditCtrl`|  
|[CRichEditCtrl::GetTextLength](../Topic/CRichEditCtrl::GetTextLength.md)|Extrait la longueur du texte, en caractères, dans cet objet d' `CRichEditCtrl` .  N'inclut pas le caractère NULL de fin.|  
|[CRichEditCtrl::GetTextLengthEx](../Topic/CRichEditCtrl::GetTextLengthEx.md)|Récupère le nombre de caractères ou d'octets dans la vue RichEdit.  Accepte une liste de balises pour indiquer la méthode pour déterminer la longueur du texte dans un contrôle RichEdit|  
|[CRichEditCtrl::GetTextMode](../Topic/CRichEditCtrl::GetTextMode.md)|Récupère le mode texte et l'annulation en cours de niveau d'un contrôle RichEdit.|  
|[CRichEditCtrl::GetTextRange](../Topic/CRichEditCtrl::GetTextRange.md)|Extrait la plage spécifiée du texte.|  
|[CRichEditCtrl::GetUndoName](../Topic/CRichEditCtrl::GetUndoName.md)|Récupère le type de l'opération d'annulation éventuelle.|  
|[CRichEditCtrl::GetWordWrapMode](../Topic/CRichEditCtrl::GetWordWrapMode.md)|Récupère les options actuelles de retour automatique à la ligne et d'analyse lexicale pour le contrôle RichEdit.  Ce message est uniquement disponible dans les versions linguistiques du système d'exploitation.|  
|[CRichEditCtrl::HideSelection](../Topic/CRichEditCtrl::HideSelection.md)|Affiche ou masque la sélection actuelle.|  
|[CRichEditCtrl::LimitText](../Topic/CRichEditCtrl::LimitText.md)|Limite la quantité de texte qu'un utilisateur peut entrer dans `CRichEditCtrl` l'objet.|  
|[CRichEditCtrl::LineFromChar](../Topic/CRichEditCtrl::LineFromChar.md)|Détermine que la ligne contient le caractère donné.|  
|[CRichEditCtrl::LineIndex](../Topic/CRichEditCtrl::LineIndex.md)|Récupère l'index du caractère d'une ligne donnée cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::LineLength](../Topic/CRichEditCtrl::LineLength.md)|Extrait la longueur d'une ligne donnée cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::LineScroll](../Topic/CRichEditCtrl::LineScroll.md)|Fait défiler le texte de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::Paste](../Topic/CRichEditCtrl::Paste.md)|Insère le contenu du presse\-papiers dans ce contrôle RichEdit.|  
|[CRichEditCtrl::PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md)|Insère le contenu du presse\-papiers dans ce contrôle RichEdit dans le format de données spécifié.|  
|[CRichEditCtrl::PosFromChar](../Topic/CRichEditCtrl::PosFromChar.md)|Récupère les coordonnées de la zone cliente d'un caractère spécifié dans un contrôle d'édition.|  
|[CRichEditCtrl::Redo](../Topic/CRichEditCtrl::Redo.md)|Refait l'action suivante dans la file d'attente de rétablissement du contrôle.|  
|[CRichEditCtrl::ReplaceSel](../Topic/CRichEditCtrl::ReplaceSel.md)|Remplace la sélection actuelle dans cet objet d' `CRichEditCtrl` par le texte spécifié.|  
|[CRichEditCtrl::RequestResize](../Topic/CRichEditCtrl::RequestResize.md)|Force cet objet d' `CRichEditCtrl` pour envoyer la demande se redimensionnent des notifications.|  
|[CRichEditCtrl::SetAutoURLDetect](../Topic/CRichEditCtrl::SetAutoURLDetect.md)|Indique si la détection automatique d'URL est actif dans un contrôle RichEdit.|  
|[CRichEditCtrl::SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md)|Définit la couleur d'arrière\-plan de cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md)|Définit les attributs de mise en forme de caractère par défaut présents dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md)|Définit le masque d'événements pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetModify](../Topic/CRichEditCtrl::SetModify.md)|Définit ou espaces libres la balise de modification pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetOLECallback](../Topic/CRichEditCtrl::SetOLECallback.md)|Définit l'objet COM d' `IRichEditOleCallback` pour ce contrôle RichEdit.|  
|[CRichEditCtrl::SetOptions](../Topic/CRichEditCtrl::SetOptions.md)|Définit les options pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md)|Définit les attributs de mise en forme de paragraphe dans la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetPunctuation](../Topic/CRichEditCtrl::SetPunctuation.md)|Définit les caractères de ponctuation pour un contrôle RichEdit.  Ce message est uniquement disponible dans les versions linguistiques du système d'exploitation.|  
|[CRichEditCtrl::SetReadOnly](../Topic/CRichEditCtrl::SetReadOnly.md)|Définit l'option en lecture seule pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetRect](../Topic/CRichEditCtrl::SetRect.md)|Définit le rectangle de mise en forme pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetSel](../Topic/CRichEditCtrl::SetSel.md)|Définit la sélection dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md)|Définit les attributs de mise en forme de caractères dans la sélection actuelle dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md)|Définit le périphérique de sortie cible pour cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetTextMode](../Topic/CRichEditCtrl::SetTextMode.md)|Définit le mode texte ou l'annulation de niveau d'un contrôle RichEdit.  Le message échec si le contrôle contient le texte.|  
|[CRichEditCtrl::SetUndoLimit](../Topic/CRichEditCtrl::SetUndoLimit.md)|Définit le nombre maximal d'actions qui peuvent stocker dans la file d'attente d'annulation.|  
|[CRichEditCtrl::SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md)|Définit les attributs de mise en forme de caractère du mot actuel dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::SetWordWrapMode](../Topic/CRichEditCtrl::SetWordWrapMode.md)|Définit le retour automatique à la ligne et les options d'analyse lexicale pour le contrôle RichEdit.  Ce message est uniquement disponible dans les versions linguistiques du système d'exploitation.|  
|[CRichEditCtrl::StopGroupTyping](../Topic/CRichEditCtrl::StopGroupTyping.md)|Arrête le contrôle de la collecte des actions supplémentaires en tapant l'opération d'annulation actuelle.  Le contrôle stocke l'action suivante tapante, le cas échéant, dans une nouvelle action dans la file d'attente d'annulation.|  
|[CRichEditCtrl::StreamIn](../Topic/CRichEditCtrl::StreamIn.md)|Insère le texte d'un flux d'entrée dans cet objet d' `CRichEditCtrl` .|  
|[CRichEditCtrl::StreamOut](../Topic/CRichEditCtrl::StreamOut.md)|Stocke le texte de cet objet d' `CRichEditCtrl` dans un flux de sortie.|  
|[CRichEditCtrl::Undo](../Topic/CRichEditCtrl::Undo.md)|Inverse la dernière opération de modification.|  
  
## Notes  
 Un « contrôle RichEdit » est une fenêtre dans laquelle l'utilisateur peut entrer et modifier le texte.  Le texte peut être assigné le caractère et la mise en forme de paragraphe, et peut inclure des objets OLE incorporé.  Les contrôles richedit fournissent une interface de programmation pour le texte de mise en forme.  Toutefois, une application doit implémenter tous les composants d'interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l'utilisateur.  
  
 Les contrôles communs Windows \(et par conséquent la classe d' `CRichEditCtrl` \) est disponible uniquement aux programmes s'exécutant sous les versions de Windows 3,51 95\/98 et Windows NT et versions ultérieures.  La classe d' `CRichEditCtrl` prend en charge les versions 2,0 et 3,0 du contrôle RichEdit d' [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] .  
  
> [!CAUTION]
>  Si vous utilisez un contrôle RichEdit dans une boîte de dialogue \(sans se soit si votre application est, une interface SDI, MDI ou basée sur des boîtes de dialogue\), vous devez appeler [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) une fois avant la boîte de dialogue s'affiche.  Un emplacement standard pour appeler cette fonction se trouve dans la fonction membre d' `InitInstance` de votre programme.  Vous n'avez pas besoin de l'appeler pour chaque fois que vous affichez la boîte de dialogue, seule la première fois.  Vous ne devez pas appeler `AfxInitRichEdit` si vous utilisez `CRichEditView`.  
  
 Pour plus d'informations sur l'utilisation `CRichEditCtrl`, consultez :  
  
-   [Contrôles](../../mfc/controls-mfc.md)  
  
-   [Utilisation CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   Article de la Base de connaissances Q259949 : LES INFO : SetCaretPos\(\) n'est pas approprié avec CEdit ou contrôles de CRichEditCtrl  
  
 Pour obtenir un exemple d'utilisation d'un contrôle RichEdit dans une application MFC, consultez l'exemple d'application de [WORDPAD](../../top/visual-cpp-samples.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [exemple MFC WORDPAD](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)
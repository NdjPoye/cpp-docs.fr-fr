---
title: "Documents multipages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo (structure), documents multipages"
  - "pages de document et pages d'imprimante"
  - "documents, paginer"
  - "documents, imprimer"
  - "DoPreparePrinting (méthode) et pagination"
  - "documents multipages"
  - "OnBeginPrinting (méthode)"
  - "OnDraw (méthode), imprimer"
  - "OnEndPrinting (méthode)"
  - "OnPrepareDC (méthode)"
  - "OnPreparePrinting (méthode)"
  - "OnPrint (méthode)"
  - "substituer, fonctions de la classe View pour impression"
  - "pages, imprimer"
  - "pagination"
  - "pagination, imprimer des documents multipages"
  - "imprimante (mode)"
  - "imprimantes, imprimante (mode)"
  - "imprimer (MFC), documents multipages"
  - "imprimer (MFC), pagination"
  - "imprimer (MFC), protocole"
  - "protocoles, impression (protocole)"
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Documents multipages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique aux fenêtres comment imprimer le protocole et explique comment imprimer des documents qui contiennent plusieurs pages.  L'article couvre les rubriques suivantes:  
  
-   [Protocole d'impression](#_core_the_printing_protocol)  
  
-   [Remplacement des fonctions de la classe d'affichage](#_core_overriding_view_class_functions)  
  
-   [Pagination](#_core_pagination)  
  
-   [pages de document contre pages d'imprimante](#_core_printer_pages_vs.._document_pages)  
  
-   [Pagination de temps impression](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a> Le protocole d'impression  
 Pour imprimer un document en comprend plusieurs, l'infrastructure et l'affichage interactif de la façon suivante.  Tout d'abord l'infrastructure affiche la boîte de dialogue **Print**, crée un contexte de périphérique pour l'imprimante, puis appelle la fonction membre [StartDoc](../Topic/CDC::StartDoc.md) de l'objet [CDC](../mfc/reference/cdc-class.md).  Ensuite, chaque page du document, l'infrastructure requiert une fonction membre [StartPage](../Topic/CDC::StartPage.md) de l'objet `CDC`, demande à l'objet de vue d'imprimer la page, puis appelle la fonction membre [EndPage](../Topic/CDC::EndPage.md).  Si le mode d'impression doit être modifié avant de démarrer une page spécifique, elle appelle [ResetDC](../Topic/CDC::ResetDC.md), qui met à jour la structure [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) contenant les nouvelles informations du mode d'imprimante.  Lorsque le document entier a été écrit, l'infrastructure appelle la fonction membre [EndDoc](../Topic/CDC::EndDoc.md).  
  
##  <a name="_core_overriding_view_class_functions"></a> Remplacement des fonctions de la classe d'affichage  
 La classe [CView](../mfc/reference/cview-class.md) définit plusieurs fonctions membres qui est appelée par l'infrastructure lors de l'impression.  Lorsque vous remplacez ces fonctions dans la classe d'affichage, fournissez les connexions la logique de l'impression entre la logique imprimante de l'infrastructure et de la classe d'affichage.  Le tableau suivant répertorie ces fonctions membres.  
  
### Les fonctions substituables de CView pour l'impression  
  
|Nom|Raison pour remplacer|  
|---------|---------------------------|  
|[OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|Pour insérer des valeurs dans la boîte de dialogue Imprimer, notamment la longueur du document|  
|[OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|Pour allouer les polices ou d'autres ressources GDI|  
|[OnPrepareDC](../Topic/CView::OnPrepareDC.md)|Pour paramétrer les attributs du contexte de périphérique pour une page spécifique, ou calculer la pagination de temps impression|  
|[OnPrint](../Topic/CView::OnPrint.md)|Pour imprimer une page de données|  
|[OnEndPrinting](../Topic/CView::OnEndPrinting.md)|Pour libérer des ressources GDI|  
  
 Vous pouvez effectuer un traitement impression\- liés dans d'autres fonctions également, mais ces fonctions sont celles qui pilotent le processus d'impression.  
  
 L'illustration suivante montre les étapes impliquées dans le processus d'impression et indique où chaque `CView` de fonctions membres d'impression est appelé.  Le reste de cet article explique la plupart de ces étapes plus en détail.  Les éléments supplémentaires du processus d'impression sont décrites dans l'article [Allouer des ressources GDI](../mfc/allocating-gdi-resources.md).  
  
 ![Processus de boucle d'impression](../mfc/media/vc37c71.png "vc37C71")  
La boucle d'impression  
  
##  <a name="_core_pagination"></a> Pagination  
 L'infrastructure stocke une grande partie des informations sur un travail d'impression d'une structure [CPrintInfo](../mfc/reference/cprintinfo-structure.md).  Plusieurs valeurs dans `CPrintInfo` se rapportent à la pagination ; ces valeurs sont accessibles comme indiqué dans le tableau suivant.  
  
### Les informations de numéro de page stockées dans CPrintInfo  
  
|Variable membre ou<br /><br /> Nom\(s\) de la fonction|Numéro de page référencée|  
|----------------------------------------------------|-------------------------------|  
|`GetMinPage`\/`SetMinPage`|Première page du document|  
|`GetMaxPage`\/`SetMaxPage`|Dernière page du document|  
|`GetFromPage`|Première page à imprimer|  
|`GetToPage`|Dernière page à imprimer|  
|`m_nCurPage`|Page actuellement imprimée|  
  
 Les numéros de page commence à 1, c'est\-à\-dire, la première page est comptée 1, et non à 0.  Pour plus d'informations sur ces et d'autres membres [CPrintInfo](../mfc/reference/cprintinfo-structure.md), consultez *le guide de MFC*.  
  
 Au début du processus d'impression, l'infrastructure appelle la fonction membre [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) de la vue, en passant un pointeur vers une structure d'`CPrintInfo`.  L'Application fournit une implémentation de `OnPreparePrinting` qui appelle [DoPreparePrinting](../Topic/CView::DoPreparePrinting.md), une autre fonction membre `CView`.  `DoPreparePrinting` est la fonction qui affiche la boîte de dialogue Imprimer et crée un contexte de l'imprimante.  
  
 À ce stade l'application ne connaît pas le nombre de pages dans le document.  Elle utilise les valeurs par défaut 1 et 0xFFFF pour les numéros des première et la dernière page du document.  Si vous connaissez le nombre de pages votre document a, remplacez `OnPreparePrinting` et l'appel [SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md) de la structure `CPrintInfo` avant de l'envoyiez à `DoPreparePrinting`.  Cela vous permet de spécifier la longueur du document.  
  
 `DoPreparePrinting` puis affiche la boîte de dialogue Imprimer.  Lorsque la valeur est renvoyée, la structure `CPrintInfo` contient les valeurs spécifiées par l'utilisateur.  Si les souhaits utilisateur pour imprimer une seule plage sélectionnée les pages, de la ou de la peuvent spécifier des numéros de page démarrants et de fin dans la boîte de dialogue Imprimer.  L'infrastructure récupère ces valeurs à l'aide des fonctions `GetFromPage` et `GetToPage` de [CPrintInfo](../mfc/reference/cprintinfo-structure.md).  Si l'utilisateur ne spécifie pas d'étendue de pages, l'infrastructure appelle `GetMinPage` et `GetMaxPage` et utilise les valeurs retournées pour imprimer le document.  
  
 Pour chaque page du document à imprimer, l'infrastructure appelle deux fonctions membres de la classe d'affichage, [OnPrepareDC](../Topic/CView::OnPrepareDC.md) et [OnPrint](../Topic/CView::OnPrint.md), puis passe des paramètres de chaque fonction deux : pointeur vers un objet [CDC](../mfc/reference/cdc-class.md) et un pointeur vers une structure `CPrintInfo`.  Chaque fois que l'infrastructure appelle `OnPrepareDC` et `OnPrint`, elle transmet une valeur différente du membre `m_nCurPage` de la structure `CPrintInfo`.  De cette manière l'interface indique à l'affichage quelle page doit être imprimée.  
  
 La fonction membre [OnPrepareDC](../Topic/CView::OnPrepareDC.md) est également utilisée pour l'écran.  Il comporte des ajustements dans le contexte de périphérique avant d'ajouter a lieu.  `OnPrepareDC` sert un rôle semblable à l'impression, mais il existe des différences : d'abord, l'objet `CDC` représente le contexte de l'imprimante au lieu d'un contexte de périphérique, et ensuite, un objet `CPrintInfo` est transmis en tant que second paramètre. \(Ce paramètre est **NULL** lorsque `OnPrepareDC` est appelé pour l'écran.\) Remplacez `OnPrepareDC` pour effectuer des ajustements dans le contexte de périphérique sur lequel la page est imprimée.  Par exemple, vous pouvez déplacer l'origine de la fenêtre d'affichage et la zone de segment pour garantir que la partie pertinente du document est imprimée.  
  
 La fonction membre [OnPrint](../Topic/CView::OnPrint.md) effectue l'impression réelle de la page.  L'article [Comment avez par défaut l'impression est effectuée](../mfc/how-default-printing-is-done.md) montre comment l'infrastructure appelle [OnDraw](../Topic/CView::OnDraw.md) avec un contexte de l'imprimante pour effectuer une impression.  Plus précisément, les appels `OnPrint` framework à une structure `CPrintInfo` et un contexte de périphérique, et exécute `OnPrint` le contexte de périphérique à `OnDraw`.  Remplacez `OnPrint` pour exécuter tout rendu qui doit être effectuée uniquement lors de l'impression et pas pour l'écran.  Par exemple, pour imprimer les en\-têtes ou pieds de page \(consultez l'article [En\-têtes et pieds de page](../mfc/headers-and-footers.md) pour plus d'informations\).  L'appel `OnDraw` de la substitution de `OnPrint` pour effectuer les opérations courantes de rendu à l'écran et l'impression.  
  
 Le fait que `OnDraw` effectue le rendu de l'écran et l'impression signifie que votre application est WYSIWYG : « Qui s'affiche est que vous obtenez ». Toutefois, supposons que vous n'entrez pas une application de WYSIWYG.  Par exemple, considérez un éditeur de texte qui utilise une police en gras pour les codes de contrôle d'impression et de vues présentent des caractères gras à l'écran.  Dans ce type de situation, vous utilisez `OnDraw` strictement pour l'écran.  Lorsque vous remplacez `OnPrint`, remplacez l'appel à `OnDraw` par un appel à une fonction distinct de dessin.  La fonction dessine le document la méthode il apparaît dans le document, à l'aide de les attributs que vous ne pas afficher à l'écran.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a> Pages de document contre pages d'imprimante  
 Lorsque vous faites référence à des numéros de page, il est parfois nécessaire de distinguer le concept de l'impression d'une page et le concept d'un document d'une page.  Du point de vue de l'imprimante, une page est une feuille de papier.  Toutefois, une feuille de papier n'est pas nécessairement une page du document.  Par exemple, si vous imprimez un bulletin d'informations, où les feuilles doivent être pliées, une feuille de papier peut contenir les première et dernière pages du document, côte à côte.  De même, si vous imprimez une feuille de calcul, le document ne comprend pas les pages du tout.  En revanche, une feuille de papier peut contenir des lignes 1 à 20, les colonnes 6 et 10.  
  
 Tous les numéros de page dans la structure [CPrintInfo](../mfc/reference/cprintinfo-structure.md) font référence aux pages d'imprimante.  L'infrastructure appelle `OnPrepareDC` et `OnPrint` une fois pour chaque feuille de papier qui traversera l'imprimante.  Lorsque vous remplacez la fonction [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) pour spécifier la longueur du document, vous devez utiliser les pages d'imprimante.  S'il existe une correspondance un\-à\-un \(autrement dit, une page d'impression est égal à une page de document\), alors il est facile.  Si, en revanche, les pages de documents et d'imprimante ne correspondent pas directement, vous devez convertir entre elles.  Par exemple, pensez à imprimer une feuille de calcul.  En remplaçant `OnPreparePrinting`, vous devez calculer le nombre de feuilles de papier sont requises pour imprimer la feuille de calcul entière puis utiliser cette valeur en appelant la fonction membre `SetMaxPage` de `CPrintInfo`.  De même, en remplaçant `OnPrepareDC`, vous devez convertir `m_nCurPage` dans une plage de lignes et les colonnes qui apparaissent sur cette feuille spécifique puis régleront l'origine de la fenêtre d'affichage en conséquence.  
  
##  <a name="_core_print.2d.time_pagination"></a> Pagination de temps impression  
 Dans certains cas, la classe d'affichage ne peut pas savoir à l'avance le temps le document est tant qu'il n'a pas été imprimé.  Par exemple, supposons que votre application n'est pas WYSIWYG, donc une longueur document à l'écran ne correspond pas à sa longueur une fois imprimée.  
  
 Ceci pose un problème lorsque vous remplacez [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) pour votre classe d'affichage : vous ne pouvez pas passer une valeur à la fonction `SetMaxPage` de la structure [CPrintInfo](../mfc/reference/cprintinfo-structure.md), parce que vous ne connaissez pas la longueur du document.  Si l'utilisateur ne spécifie pas un numéro de page pour arrêter à utiliser la boîte de dialogue Imprimer, l'infrastructure ne connaît pas arrêter lorsque la boucle d'impression.  La seule façon de déterminer quand arrêter la boucle d'impression est pour imprimer le document et de voir lorsqu'elle se termine.  La classe d'affichage doit vérifier la fin de le document lorsqu'il est imprimée, puis notifier l'infrastructure lorsque la fin est atteinte.  
  
 L'infrastructure s'appuie sur la fonctionnalité de [OnPrepareDC](../Topic/CView::OnPrepareDC.md) de la classe d'affichage pour l'afficher lorsque arrêter.  Après chaque appel à `OnPrepareDC`, l'infrastructure active un membre de la structure `CPrintInfo` appelée `m_bContinuePrinting`.  Sa valeur par défaut est **VRAI**. Dès lors qu'elle reste ainsi, l'infrastructure la boucle continue d'impression.  Si elle a la valeur **FALSE**, l'infrastructure s'arrête.  Pour effectuer la pagination de impression temps, la substitution `OnPrepareDC` pour vérifier si la fin du document a été atteinte, et l'ensemble `m_bContinuePrinting` à **FALSE** lorsqu'il a.  
  
 L'implémentation par défaut de `OnPrepareDC` définit `m_bContinuePrinting` à **FALSE** si la page actuelle est supérieure à 1.  Cela signifie que si la longueur du document n'est pas spécifiée, l'infrastructure suppose que le document est une page de.  Une conséquence de ce fait que vous devez prendre soin si vous appelez la version de la classe de base de `OnPrepareDC`.  Ne voulez pas que `m_bContinuePrinting` est **TRUE** après avoir appelé la version de la classe de base.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [En\-têtes et pieds de page](../mfc/headers-and-footers.md)  
  
-   [Allocation de ressources GDI](../mfc/allocating-gdi-resources.md)  
  
## Voir aussi  
 [Impression](../mfc/printing.md)   
 [CView Class](../mfc/reference/cview-class.md)   
 [CDC, classe](../mfc/reference/cdc-class.md)
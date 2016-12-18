---
title: "TN016&#160;: utilisation de l&#39;h&#233;ritage multiple C++ avec MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MI (Multiple Inheritance)"
  - "héritage multiple, prise en charge des MFC pour"
  - "TN016"
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
caps.latest.revision: 22
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN016&#160;: utilisation de l&#39;h&#233;ritage multiple C++ avec MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit l'utilisation de l'héritage multiple \(MI\) avec les Microsoft Foundation Classes.  L'utilisation du MI n'est pas nécessaire avec MFC.  Le MI n'est pas utilisé dans les classes MFC et n'est pas nécessaire pour écrire une bibliothèque de classes.  
  
 Les sous\-rubriques ci\-dessous expliquent comment le MI affecte l'utilisation des idiomes courants de MFC et couvre certaines restrictions de MI.  Certaines de ces restrictions sont des restrictions générales du C\+\+.  D'autres sont imposées par l'architecture MFC.  
  
 À la fin de cette note technique vous trouverez une application complète MFC qui utilise le MI.  
  
## CRuntimeClass  
 Les mécanismes de création d'objet permanent et dynamique de MFC utilisent la structure de données [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) pour identifier les classes.  MFC associe une de ces structures à chaque classe dynamique et\/ou sérialisable dans votre application.  Ces structures sont initiées au démarrage de l'application à l'aide d'un objet statique spécial de type `AFX_CLASSINIT`.  
  
 L'implémentation actuelle de `CRuntimeClass` ne prend pas en charge les informations de type MI lors de l'exécution.  Cela ne signifie pas que vous ne pouvez pas utiliser MI dans votre application MFC.  Toutefois, vous aurez des responsabilités lorsque vous utilisez des objets qui ont plusieurs classes de base.  
  
 La méthode [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) ne détermine pas correctement le type d'un objet s'il a plusieurs classes de base.  Par conséquent, vous ne pouvez pas utiliser [CObject](../mfc/reference/cobject-class.md) en tant que classe de base virtuelle, et les appels aux méthodes `CObject` telles que [CObject::Serialize](../Topic/CObject::Serialize.md) et [CObject::operator new](../Topic/CObject::operator%20new.md) doivent posséder des qualificateurs d'étendue afin que C\+\+ puisse lever toute ambiguïté dans l'appel de fonction approprié.  Lorsqu'un programme utilise le MI dans MFC, la classe qui contient la classe de base `CObject` doit être la classe de gauche dans la liste des classes de base.  
  
 Une alternative est d'utiliser l'opérateur `dynamic_cast`.  La conversion d'un objet avec MI en l'une de ses classes de base force le compilateur à utiliser les fonctions de la classe de base fournie.  Pour plus d'informations, consultez [dynamic\_cast, opérateur](../cpp/dynamic-cast-operator.md).  
  
## CObject \- la racine de toutes les classes  
 Toutes les classes importantes dérive directement ou indirectement de la classe `CObject`.  `CObject` n'a pas d'attributs, mais a certaines fonctionnalités par défaut.  Lorsque vous utilisez le MI, vous hériterez généralement de deux classes dérivées de `CObject` ou plus.  L'exemple suivant montre comment une classe peut hériter de [CFrameWnd](../mfc/reference/cframewnd-class.md) et de [CObList](../mfc/reference/coblist-class.md):  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 Dans ce cas `CObject` est inclus deux fois.  Cela signifie que vous avez besoin d'une méthode pour lever l'ambiguïté dans toute référence à des méthodes ou aux opérateurs `CObject`.  `operator new` et [operator delete](../Topic/CObject::operator%20delete.md) sont deux opérateurs qui doivent être désambiguïsés.  À titre d'autre exemple, le code suivant génère une erreur de compilation :  
  
```  
myListWnd.Dump(afxDump);  
    // compile time error, CFrameWnd::Dump or CObList::Dump ?  
```  
  
## Réimplanter des méthodes CObject  
 Lorsque vous créez une classe qui contient deux classes de base dérivées de `CObject` ou plus, vous devez réimplementer les méthodes de `CObject` que vous voulez que d'autres personnes utilisent.  Les opérateurs `new` et `delete` sont obligatoires et [Dump](../Topic/CObject::Dump.md) est recommandé.  L'exemple suivant réimplémente les opérateurs `new` et `delete` et la méthode `Dump`:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    void Dump(CDumpContent& dc)  
        { CFrameWnd::Dump(dc);  
          CObList::Dump(dc); }  
     ...  
};  
```  
  
## Héritage virtuel de CObject  
 Il peut sembler qu'hériter virtuellement `CObject` résoudrait le problème de l'ambiguïté de fonction, mais ce n'est pas le cas.  Étant donné qu'il n'y a pas d'attributs dans `CObject`, vous n'avez pas besoin d'héritage virtuel pour éviter plusieurs copies d'un attribut de la classe de base.  Dans le premier exemple qui a été indiqué précédemment, la méthode virtuelle `Dump` est toujours ambiguë parce qu'elle est implémentée différemment dans `CFrameWnd` et `CObList`.  La meilleure méthode pour éclaircir l'ambiguïté consiste à suivre les règles présentées dans la section précédente.  
  
## CObject::IsKindOf et saisie à l'exécution  
 Le mécanisme de saisie à l'exécution pris en charge par MFC dans `CObject` utilise les macros `DECLARE_DYNAMIC`, `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE`, `IMPLEMENT_DYNCREATE`, `DECLARE_SERIAL` et `IMPLEMENT_SERIAL`.  Ces macros peuvent effectuer une vérification de type d'exécution pour vous assurer que les conversions en aval sont sécurisées.  
  
 Les macros prennent en charge une seule classe de base et s'exécutent de façon limitée pour multiplier les classes héritées.  La classe de base que vous spécifiez dans `IMPLEMENT_DYNAMIC` ou `IMPLEMENT_SERIAL` doit être la première \(ou la plus à gauche\) classe de base.  Ce positionnement vous permet de faire une vérification de type de la classe de base à gauche uniquement.  Le système de types d'exécution ne saura rien sur les classes de base supplémentaires.  Dans l'exemple suivant, les systèmes d'exécution feront la vérification de type sur `CFrameWnd`, mais ne connaîtront rien sur `CObList`.  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
    DECLARE_DYNAMIC(CListWnd)  
    ...  
};  
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)  
```  
  
## CWnd et tables de messages  
 Pour que le système de table de messages MFC fonctionne correctement, il existe deux autres conditions requises :  
  
-   Il doit n'y avoir qu'une classe de base dérivée de `CWnd`.  
  
-   La classe de base dérivée de `CWnd` doit être la première \(ou la plus à gauche\) classe de base.  
  
 Voici quelques exemples qui ne fonctionnent pas :  
  
```  
class CTwoWindows : public CFrameWnd, public CEdit  
    { ... };  
        // error : two copies of CWnd  
  
class CListEdit : public CObList, public CEdit  
    { ... };  
        // error : CEdit (derived from CWnd) must be first  
```  
  
## Un exemple de programme utilisant le MI  
 L'exemple suivant est une application autonome qui se compose d'une classe dérivée de `CFrameWnd` et de [CWinApp](../mfc/reference/cwinapp-class.md).  Nous déconseillons que vous structuriez une application de cette manière, mais il s'agit d'un exemple de la plus petite application MFC qui a une classe.  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
    // Necessary because of MI disambiguity  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    // Implementation  
    // CWinApp overrides  
    virtual BOOL InitInstance();  
    // CFrameWnd overrides  
    virtual void PostNcDestroy();  
    afx_msg void OnPaint();  
  
    DECLARE_MESSAGE_MAP()  
  
};  
  
BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)  
    ON_WM_PAINT()  
END_MESSAGE_MAP()  
  
// because the frame window is not allocated on the heap, we must  
// override PostNCDestroy not to delete the frame object  
void CHelloAppAndFrame::PostNcDestroy()  
{  
    // do nothing (do not call base class)  
}  
  
void CHelloAppAndFrame::OnPaint()  
{  
    CPaintDC dc(this);  
    CRect rect;  
    GetClientRect(rect);  
  
    CString s = "Hello, Windows!";  
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);  
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));  
    dc.SetBkMode(TRANSPARENT);  
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);  
}  
  
// Application initialization  
BOOL CHelloAppAndFrame::InitInstance()  
{  
    // first create the main frame  
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",  
        WS_OVERLAPPEDWINDOW, rectDefault))  
        return FALSE;  
  
    // the application object is also a frame window  
    m_pMainWnd = this;            
    ShowWindow(m_nCmdShow);  
    return TRUE;  
}  
  
CHelloAppAndFrame theHelloAppAndFrame;  
```  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
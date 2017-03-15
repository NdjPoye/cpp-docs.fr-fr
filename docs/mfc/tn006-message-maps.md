---
title: "TN006&#160;: tables des messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.messages.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables des messages (C++), messagerie Windows"
  - "ON_COMMAND (macro)"
  - "ON_COMMAND_EX (macro)"
  - "ON_COMMAND_RANGE (macro)"
  - "ON_COMMAND_RANGE_EX (macro)"
  - "ON_CONTROL (macro)"
  - "ON_CONTROL_RANGE (macro)"
  - "ON_MESSAGE (macro)"
  - "ON_NOTIFY (message)"
  - "ON_NOTIFY_RANGE (macro)"
  - "ON_REGISTERED_MESSAGE (macro)"
  - "ON_UPDATE_COMMAND_UI (macro)"
  - "TN006"
  - "messages Windows (C++), tables des messages"
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# TN006&#160;: tables des messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les map de messages de MFC.  
  
## Le problème  
 Microsoft Windows implémente des fonctions virtuelles dans les classes de fenêtres utilisant son système de messagerie.  En raison du grand nombre de messages impliqués, fournir une fonction virtuelle distincte pour chaque message windows crée une table prohibitivement volumineuse.  
  
 Puisque le nombre de messages définis par le système Windows varie dans le temps, et comme les applications peuvent définir leurs propres messages Windows, les tables des messages fournissent un niveau d'adressage indirect qui empêche les modifications de l'interface de désactiver le code existant.  
  
## Vue d'ensemble  
 MFC fournit une alternative au relevé de bascule utilisé dans les programmes Windows traditionnels pour traiter les messages envoyés dans une fenêtre.  Un mappage des messages à des méthodes peut être défini de sorte que lorsqu'un message est reçu par une fenêtre, la méthode appropriée est appelée automatiquement.  Cette fonctionnalité de table de messages est conçue pour ressembler aux fonctions virtuelles mais présente des avantages supplémentaires qui ne ne sont pas possibles avec des fonctions virtuelles C\+\+.  
  
## Définir une table de messages  
 La macro [DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md)déclare trois membres pour une classe.  
  
-   Tableau privé d'entrées de `AFX_MSGMAP_ENTRY` appelé `_messageEntries`.  
  
-   Une structure `AFX_MSGMAP` appelée `messageMap` qui pointe vers le tableau `_messageEntries`.  
  
-   Une fonction virtuelle protégée appelée `GetMessageMap` qui retourne l'adresse de `messageMap`.  
  
 La macro doit être placée dans la déclaration de n'importe quelle classe utilisant des tables de messages.  Par convention, c'est à la fin de la déclaration de classe.  Par exemple :  
  
```  
class CMyWnd : public CMyParentWndClass  
{  
    // my stuff...  
  
protected:  
    //{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();  
    //}}AFX_MSG  
  
    DECLARE_MESSAGE_MAP()  
};  
```  
  
 Voici le format généré par AppWizard et ClassWizard lorsqu'ils créent de nouvelles classes.  Les parenthèses \/\/{{ et \/\/}} sont nécessaires pour ClassWizard.  
  
 La table de la map de messages est définie à l'aide d'un ensemble de macros qui s'étendent aux entrées de la map de messages.  Une table démarre avec un appel de macro [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md), qui définit la classe qui est gérée par cette table de messages et la classe parente à laquelle les messages non gérés sont passés.  La table se termine avec un appel à la macro[END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md).  
  
 Entre ces deux macro, il y a une entrée pour chaque message à gérer par cette table des messages.  Chaque message Windows standard a une macro du formulaire ON\_WM\_*MESSAGE\_NAME* qui génère une entrée pour ce message.  
  
 Une signature de la fonction standard est définie pour décompresser les paramètres de chaque message Windows et assurer la cohérence des types.  Les signatures se trouvent dans le fichier Afxwin.h dans la déclaration de [CWnd](../mfc/reference/cwnd-class.md).  Chacun est marqué avec le mot clé `afx_msg` pour une identification simple.  
  
> [!NOTE]
>  ClassWizard requiert que vous utilisiez le mot clé `afx_msg` dans les déclarations du gestionnaire de table des messages.  
  
 Les signatures de la fonction ont été dérivées en utilisant une convention simple.  Le nom de la fonction commence toujours par `"On`".  Ce libellé est suivi du nom du message Windows avec le « WM\_ » supprimé et la première lettre de chaque mot passée en majuscule.  L'ordre des paramètres est `wParam` suivi de `LOWORD`\(`lParam`\) puis `HIWORD`\(`lParam`\).  Les paramètres inutilisés ne sont pas transmis.  Tous les descripteurs qui sont inclus par les classes de MFC sont convertis en pointeurs aux objets appropriés de MFC.  L'exemple suivant indique comment traiter le message `WM_PAINT` et déclencher l'appel de la fonction `CMyWnd::OnPaint` :  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    //{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT()  
    //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 La table de table des messages doit être définie en dehors de la portée d'une fonction ou définition de classe.  Elle ne doit pas être placée dans un bloc extern "C".  
  
> [!NOTE]
>  ClassWizard modifiera les entrées de la table des messages qui apparaissent entre parenthèses de commentaire \/\/{{ et \/\/}}.  
  
## Messages définis par l'utilisateur Windows  
 Les messages définis par l'utilisateur peuvent être inclus dans la table des messages à l'aide de la macro [ON\_MESSAGE](../Topic/ON_MESSAGE.md).  La macro reçoit un numéro de message et une méthode de forme :  
  
```  
    // inside the class declaration  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);  
  
    #define WM_MYMESSAGE (WM_USER + 100)  
  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 Dans cet exemple, nous établissons un gestionnaire d'un message personnalisé qui a un ID de message Windows dérivé de la base de `WM_USER` standard pour les messages définis par l'utilisateur.  L'exemple suivant montre comment appeler ce gestionnaire :  
  
```  
CWnd* pWnd = ...;  
pWnd->SendMessage(WM_MYMESSAGE);  
```  
  
 La plage des messages définis par l'utilisateur qui utilisent cette approche doit être dans la plage `WM_USER` à 0x7fff.  
  
> [!NOTE]
>  ClassWizard ne prend pas en charge l'écriture des routines du gestionnaire `ON_MESSAGE` de l'interface utilisateur de ClassWizard.  Vous devez manuellement les entrer de l'éditeur Visual C\+\+.  ClassWizard analyse ces entrées et vous permet de les parcourir comme toutes les autres entrées de la table des messages.  
  
## Messages stockés Windows  
 La fonction [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) est utilisée pour définir une nouvelle fenêtre de message qui est garantie d'être unique dans tout le système.  La Macro `ON_REGISTERED_MESSAGE` est utilisée pour traiter les messages.  La macro reçoit un nom d'une variable `UINT NEAR` qui contient l'ID du message stocké windows  Exemple :  
  
```  
class CMyWnd : public CMyParentWndClass  
{  
public:  
    CMyWnd();  
  
    //{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);  
    //}}AFX_MSG  
  
    DECLARE_MESSAGE_MAP()  
};  
  
static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");  
  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    //{{AFX_MSG_MAP(CMyWnd)  
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)  
    //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 La variable d'ID stockée de message windows \(WM\_FIND dans cet exemple\) doit être une variable `NEAR` en raison de la façon dont `ON_REGISTERED_MESSAGE` est implémenté.  
  
 La plage des messages définis par l'utilisateur qui utilisent cette approche est comprise dans la plage 0xC000 à 0xFFFF.  
  
> [!NOTE]
>  ClassWizard ne prend pas en charge l'écriture des routines du gestionnaire `ON_REGISTERED_MESSAGE` de l'interface utilisateur de ClassWizard.  Vous devez manuellement les entrer dans l'éditeur de texte.  ClassWizard analyse ces entrées et vous permet de les parcourir comme toutes les autres entrées de la table des messages.  
  
## OCM\_COMMAND \(message\)  
 Les messages de commandes des menus et des accélérateurs sont traités dans les tables de messages avec la macro `ON_COMMAND`.  La macro accepte un ID de commande et une méthode.  Seul le message spécifique `WM_COMMAND` qui a un `wParam` égal à l'ID de commande spécifié est traité par la méthode spécifiée dans l'entrée de la table des messages.  Les fonctions membres du gestionnaire de commandes n'occupent aucun paramètre et retourne `void`.  La macro a le format suivant :  
  
```  
ON_COMMAND(id, memberFxn)  
```  
  
 Les messages de mise à jour de commande sont routés via le même mécanisme, mais utilisent la macro `ON_UPDATE_COMMAND_UI` à la place.  Les fonctions membres du gestionnaire de mise à jour de commande prennent un paramètre unique, un pointeur vers un objet [CCmdUI](../mfc/reference/ccmdui-class.md), et retourne `void`.  La macro a la forme  
  
```  
ON_UPDATE_COMMAND_UI(id, memberFxn)  
```  
  
 Les utilisateurs expérimentés peuvent utiliser la macro `ON_COMMAND_EX`, qui est une forme étendue des gestionnaires de messages de commande.  La macro est un surensemble de la fonctionnalité `ON_COMMAND`.  Les fonctions membres étendues du gestionnaire de commandes prennent un seul paramètre, `UINT` qui contient l'ID de commande, et retournent un `BOOL`.  La valeur de retour doit être `TRUE` pour indiquer que la commande a été gérée.  Si le routage continue à d'autres objets de la cible de la commande.  
  
 En voici quelques exemples :  
  
-   Resource.h dans \(généralement généré par Visual C\+\+\)  
  
    ```  
    #define    ID_MYCMD      100  
    #define    ID_COMPLEX    101  
    ```  
  
-   Dans la déclaration de classe  
  
    ```  
    afx_msg void OnMyCommand();  
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);  
    afx_msg BOOL OnComplexCommand(UINT nID);  
    ```  
  
-   Dans la définition de la table des messages  
  
    ```  
    ON_COMMAND(ID_MYCMD, OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)  
    ```  
  
-   dans le fichier d'implémentation de classe :  
  
    ```  
    void CMyClass::OnMyCommand()  
    {  
        // handle the command  
    }  
  
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
    {  
        // set the UI state with pCmdUI  
    }  
  
    BOOL CMyClass::OnComplexCommand(UINT nID)  
    {  
        // handle the command  
        return TRUE;  
    }  
    ```  
  
 Les utilisateurs expérimentés peuvent gérer une plage de commandes en utilisant un seul gestionnaire de commandes : [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md) ou `ON_COMMAND_RANGE_EX`.  Copnsultez la documentation produit pour plus d'information sur les macros.  
  
> [!NOTE]
>  ClassWizard prend en charge la création `ON_COMMAND` et des gestionnaires `ON_UPDATE_COMMAND_UI`, mais il ne prend pas en charge la création `ON_COMMAND_EX` ou des gestionnaires `ON_COMMAND_RANGE`.  Toutefois, l'Assistant de classe analyse et vous permet de parcourir les quatre variantes du gestionnaire de commandes.  
  
## messages de notification de contrôle  
 Les messages envoyés des contrôles enfants dans une fenêtre ont un bit d'informations supplémentaire à leur entrée de la table des messages : l'ID de contrôle  Le gestionnaire de messages spécifié dans une entrée de la table des messages est appelée uniquement si les conditions suivantes sont remplies :  
  
-   Code de notification de contrôle \(mot élevé de `lParam`\), comme BN\_CLICKED, correspond à un code de notification spécifié dans l'entrée de la table des messages.  
  
-   L'ID de contrôle\(`wParam`\) correspond à l'ID de contrôle spécifié dans l'entrée de la table des messages.  
  
 Les messages de notification de contrôle personnalisé peuvent utiliser la macro [ON\_CONTROL](../Topic/ON_CONTROL.md) pour définir une entrée de la table des messages avec un code de notification personnalisé.  La macro a la forme  
  
```  
ON_CONTROL(wNotificationCode, id, memberFxn)  
```  
  
 Pour l'utilisation avancées [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md) peut être utilisé pour traiter une notification de contrôle d'une plage de contrôles avec le même responsable.  
  
> [!NOTE]
>  ClassWizard ne prend pas en charge la création d'un gestionnaire `ON_CONTROL` ou `ON_CONTROL_RANGE` dans l'interface utilisateur.  Vous devez manuellement les entrer avec l'éditeur de texte.  ClassWizard analyse ces entrées et vous permet de les parcourir comme toutes les autres entrées de la table des messages.  
  
 Les contrôles communs Windows utilisent le [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) plus puissant pour les notifications de contrôle complexe.  Cette version de MFC a une prise en charge direct de ce nouveau message à l'aide des macros `ON_NOTIFY` et `ON_NOTIFY_RANGE`.  Copnsultez la documentation produit pour plus d'information sur les macros.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
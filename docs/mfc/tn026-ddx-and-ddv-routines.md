---
title: "TN026&#160;: routines DDX et DDV | Microsoft Docs"
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
  - "DDX"
  - "DDV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDV (validation de données de boîtes de dialogue), procédures"
  - "DDX (échange de données de boîtes de dialogue), procédures"
  - "TN026"
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN026&#160;: routines DDX et DDV
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit l'architecture de l'échange de données de dialogue \(DDX\) et de la validation des données de dialogue \(DDV\).  Elle décrit également comment vous pouvez écrire une procédure de DDX\_ ou de DDV\_ et comment vous pouvez étendre ClassWizard pour utiliser les routines.  
  
## Présentation de l'échange de données de dialogue  
 Toutes les fonctions de données de dialogue sont codées en C\+\+.  Il n'existe aucune ressource particulière ou macro magique.  Le cœur du mécanisme est une fonction virtuelle qui est redéfinie dans chaque classe de dialogue qui fait de l'échange et de la validation de données de dialogue.  Cela se trouve toujours sous cette forme :  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);    // call base class  
  
    //{{AFX_DATA_MAP(CMyDialog)  
        <data_exchange_function_call>  
        <data_validation_function_call>  
    //}}AFX_DATA_MAP  
}  
```  
  
 Les commentaires spécialement formatés AFX permettent à ClassWizard de trouver et modifier le code de cette fonction.  Le code qui n'est pas compatible avec ClassWizard doit être placé en dehors des commentaires spécialement formatés.  
  
 Dans l'exemple ci\-dessus, \<le data\_exchange\_function\_call\> se présente sous la forme :  
  
```  
DDX_Custom(pDX, nIDC, field);  
```  
  
 et \<le data\_validation\_function\_call\> est facultatif et se présente sous la forme :  
  
```  
DDV_Custom(pDX, field, ...);  
```  
  
 Plusieurs paires de DDX\_\/DDV\_ peuvent être incluses dans une fonction `DoDataExchange`.  
  
 Consultez « afxdd\_.h » pour obtenir une liste de toutes les routines d'échange de données de dialogue et routines de validation des données de dialogue fournies de MFC.  
  
 Les données de dialogue sont tout simplement : les données membres de la classe de **CMyDialog**.  Elles ne sont pas stockées dans une structure ou quoique ce soit de similaire.  
  
## Remarques  
 Bien que nous appelions ceci « données de dialogue, » toutes les fonctionnalités sont disponibles dans n'importe quelle classe dérivée de `CWnd` et ne sont pas limitées simplement aux dialogues.  
  
 Les valeurs initiales des données sont définies dans le constructeur standard C\+\+, en général dans un bloc avec `//{{AFX_DATA_INIT` et des commentaires `//}}AFX_DATA_INIT`.  
  
 `CWnd::UpdateData` est l'opération qui effectue l'initialisation et la gestion des erreurs autour de l'appel à `DoDataExchange`.  
  
 Vous pouvez appeler `CWnd::UpdateData` à tout moment pour exécuter l'échange et la validation des données.  Par défaut `UpdateData`\(TRUE\) est appelé dans le gestionnaire par défaut de `CDialog::OnOK` et `UpdateData`\(FALSE\) est appelé dans `CDialog::OnInitDialog`par défaut.  
  
 La routine DDV\_ doit suivre immédiatement la routine DDX\_ pour ce *champ*.  
  
## Comment cela fonctionne\-t\-il ?  
 Vous n'avez pas besoin de comprendre le code suivant pour utiliser des données de dialogue.  Toutefois, la compréhension de comment cela fonctionne en arrière\-plan vous aidera à écrire votre propre processus d'échange ou de validation.  
  
 La fonction membre de `DoDataExchange` est comme la fonction membre de `Serialize` \- elle est chargée d'obtenir ou de définir les données vers\/depuis un formulaire externe \(dans ce cas, des contrôles dans un dialogue\) depuis\/vers des données membres de la classe.  Le paramètre `pDX` est le contexte pour effectuer l'échange des données et est semblable au paramètre `CArchive` de `CObject::Serialize`.  L'objet `pDX` \(un objet `CDataExchange` \) a un indicateur de direction comme `CArchive` a une balise de direction :  
  
-   Si **\!m\_bSaveAndValidate**, alors charge l'état des données dans les contrôles.  
  
-   Si `m_bSaveAndValidate`, alors définit l'état des données à partir des contrôles.  
  
 La validation se produit uniquement lorsque `m_bSaveAndValidate` est défini.  La valeur de `m_bSaveAndValidate` est déterminée par le paramètre de BOOL de `CWnd::UpdateData`.  
  
 Il existe trois autres membres intéressants de `CDataExchange`:  
  
-   `m_pDlgWnd`: La fenêtre \(généralement un dialogue\) qui contient les contrôles.  Cela permet d'éviter aux appelants des fonctions globales DDX\_ et DDV\_ de passer « this » à chaque routine de DDX\/DDV.  
  
-   `PrepareCtrl`, et `PrepareEditCtrl`: Prépare un contrôle du dialogue pour l'échange des données.  Stocke le handle de ce contrôle pour définir le focus si une validation échoue.  `PrepareCtrl` est utilisé pour les contrôles nonedit et `PrepareEditCtrl` est utilisé pour les contrôles edit.  
  
-   **Échec**: Appelé après avoir fait apparaître une boite message alertant l'utilisateur de l'erreur d'entrée.  Cette routine restaure le focus sur le dernier contrôle \(le dernier appel à `PrepareCtrl`\/`PrepareEditCtrl`\) et lève une exception.  Cette fonction membre peut être appelée depuis les routines DDX\_ et DDV\_.  
  
## Extensions utilisateur  
 Il existe plusieurs façons d'étendre le mécanisme DDX\/DDV par défaut.  Vous pouvez :  
  
-   Ajouter de nouveaux types de données  
  
    ```  
    CTime  
    ```  
  
-   Ajoute de nouvelles procédures d'échange \(DDX\_ ? ? ?\).  
  
    ```  
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);  
    ```  
  
-   Ajoute de nouvelles procédures de validation \(DDV\_ ? ? ?\).  
  
    ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);  
    // make sure time is in the future or past  
    ```  
  
-   Passe des expressions arbitraires aux procédures de validation.  
  
    ```  
    DDV_MinMax(pDX, age, 0, m_maxAge);  
    ```  
  
    > [!NOTE]
    >  De telles expressions arbitraires ne peuvent pas être modifiées par ClassWizard et ne peuvent donc pas être déplacées hors de les commentaires spéciaux de format \(\/{{AFX\_DATA\_MAP \(CMyClass\).  
  
 Fait inclure à la fonction membre **DoDialogExchange** des instructions conditionnelles ou toutes autres instructions C\+\+ valides avec des appels entremêlés de fonction d'échange et de validation.  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX, IDC_SEX, m_bFemale);  
DDX_Text(pDX, IDC_EDIT1, m_age);  
//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);  
else  
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);  
```  
  
> [!NOTE]
>  Comme indiqué ci\-dessus, ce code ne peut pas être modifié par ClassWizard et doit être utilisé uniquement en dehors des commentaires spéciaux de format.  
  
## Prise en charge de ClassWizard  
 ClassWizard prend en charge un sous\-ensemble de personnalisations de DDX\/DDV en vous permettant d'intégrer vos propres routines de DDX\_ et de DDV\_ dans l'interface utilisateur de ClassWizard.  Cela n'est judicieux que si vous envisagez de réutiliser des routines spécifiques de DDX et de DDV dans un projet ou dans plusieurs projets.  
  
 Pour cela, des entrées spéciales sont écrite dans DDX.CLW \(les versions antérieures de Visual C\+\+ stockait ces informations dans APSTUDIO.INI\) ou dans le fichier de .CLW de votre projet.  Les entrées spéciales peuvent être écrites dans la section d'informations générales \[general info\] du fichier .CLW de votre projet ou dans la section \[ExtraDDX\] du fichier de DDX.CLW dans le répertoire \\program files\\Microsoft Visual Studio\\Visual C\+\+\\bin.  Vous devrez peut\-être créer le fichier DDX.CLW s'il n'existe pas déjà.  Si vous envisagez d'utiliser les routines personnalisées DDX\_\/DDV\_ uniquement dans un certain projet, ajouter des entrées dans la section d'informations générales \[general info\] de votre fichier du projet .CLW à la place.  Si vous envisagez d'utiliser les routines dans plusieurs projets, ajoutez des entrées à la section \[ExtraDDX\] de DDX.CLW.  
  
 Le format standard de ces entrées spéciales est :  
  
```  
ExtraDDXCount=n  
```  
  
 où n est le nombre d'ExtraDDX ? lignes à suivre  
  
```  
ExtraDDX?=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 où ? est un nombre entre 1 et n qui indique quel type DDX dans la liste est en train d'être défini.  
  
 Chaque champ est délimitée par « ; » caractère.  Les champs et leur objectif sont décrits ci\-dessous.  
  
 \<touches\>  
 \= liste de caractères uniques indiquant pour quels contrôles de dialogue ce type de variable est autorisé.  
  
 E \= modification  
  
 c \= case à cocher à deux états  
  
 c \= case à cocher à trois états  
  
 R \= première case d'option dans un groupe  
  
 L \= zone de liste non triée  
  
 l \= zone de liste ordonnée  
  
 M \= zone de liste déroulante \(avec l'élément de modification\)  
  
 N \= liste déroulante non triée  
  
 n \= liste déroulante triée  
  
 1 \= si l'insertion de DDX doit être effectuée en tête de la liste \(par défaut l'ajout est en fin de liste\). Généralement utilisé pour les routines de DDX qui transfèrent la propriété de contrôle.  
  
 \<VB\-keys\>  
 Ce champ est utilisé uniquement dans le produit 16 bits pour les contrôles de VBX \(les contrôles de VBX ne sont pas pris en charge dans le produit 32 bits\)  
  
 \<prompt\>  
 Chaîne à placer dans la liste modifiable des propriétés \(aucun guillemet\)  
  
 \<type\>  
 Identificateur unique à émettre par le type dans le fichier d'en\-tête.  Dans notre exemple ci\-dessus avec DDX\_Time, il sera défini avec CTime.  
  
 \<vb\-keys\>  
 Non utilisé dans cette version et doit toujours être vide  
  
 \<initValue\>  
 Valeur initiale à 0 ou vide.  Si elle est vide, alors aucune ligne d'initialisation n'est écrite dans la section \/\/{{AFX\_DATA\_INIT du fichier d'implémentation.  Une entrée vide doit être utilisée pour les objets C\+\+ \(par exemple `CString`, `CTime`, etc.\) qui ont des constructeurs qui garantissent l'initialisation correcte.  
  
 \<DDX\_Proc\>  
 Identificateur unique de la procédure de DDX\_.  Le nom de la fonction C\+\+ doit commencer par « DDX\_, » mais ne pas inclure « DDX\_ » dans l'identificateur de \<DDX\_Proc\>.  Dans l'exemple ci\-dessus, l'identificateur de \<DDX\_PROC\> est "Time".  Lorsque ClassWizard écrit l'appel de fonction dans le fichier d'implémentation dans la section {{AFX\_DATA\_MAP, elle ajoute ce nom à DDX\_, ce qui donne ainsi DDX\_Time.  
  
 \<comment\>  
 Commentaire à afficher dans la boîte de dialogue de la variable pour ce DDX.  Place tout le texte que vous souhaitez ici, et fournit habituellement quelque chose qui décrit l'opération effectuée par la paire de DDX\/DDV.  
  
 \<DDV\_Proc\>  
 La partie DDV de l'entrée est facultative.  Toutes les routines de DDX n'ont pas de routines de DDV correspondantes.  Souvent, il est plus pratique d'inclure la phase de validation comme partie entière du transfert.  C'est souvent le cas lorsque votre routine de DDV ne requiert aucun paramètre, car ClassWizard ne prend pas en charge les routines de DDV sans aucun paramètre.  
  
 \<arg\>  
 Identificateur unique de la procédure de DDV\_.  Le nom de la fonction C\+\+ doit commencer par « DDV\_, », mais ne pas inclure « DDX\_ » dans l'identificateur de \<DDX\_Proc\>.  
  
 suivi de 1 ou 2 arguments de DDV :  
  
 \<promptX\>  
 chaîne à placer au\-dessus de l'élément de modification \(avec & comme accélérateur\)  
  
 \<fmtX\>  
 caractère de format pour le type d'arg, parmi  
  
 d \= int  
  
 u \= unsigned  
  
 D \= entier long \(autrement dit, long\)  
  
 U \= long non signé \(autrement dit, DWORD\)  
  
 f \= float  
  
 F\= double  
  
 s \= chaine de caractère  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
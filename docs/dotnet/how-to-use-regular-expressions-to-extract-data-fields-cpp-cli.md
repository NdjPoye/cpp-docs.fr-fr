---
title: "Comment&#160;: extraire des champs de donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "données (C++), extraire à partir de chaînes"
  - "chaînes mises en forme (C++)"
  - "expressions régulières (C++), extraction des champs de données"
  - "chaînes (C++), récupérer les données de"
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: extraire des champs de donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'utilisation d'expressions régulières pour extraire des données d'une chaîne mise en forme.  L'exemple de code suivant utilise la classe <xref:System.Text.RegularExpressions.Regex> pour spécifier un modèle qui correspond à une adresse de messagerie.  Ce modèle inclut des identificateurs de champ qui peuvent être utilisés pour récupérer les parties de nom d'hôte et d'utilisateur de chaque adresse de messagerie.  La classe <xref:System.Text.RegularExpressions.Match> est utilisée pour exécuter les critères spéciaux réels.  Si l'adresse de messagerie donnée est valide, les noms d'hôte et nom d'utilisateur sont extraits et affichés.  
  
## Exemple  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
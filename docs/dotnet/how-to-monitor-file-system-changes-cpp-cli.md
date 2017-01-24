---
title: "Comment&#160;: surveiller les modifications de syst&#232;me de fichiers (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "événements (C++), surveiller"
  - "exemples (C++), analyser les modifications du système de fichiers"
  - "événements de système de fichiers (C++)"
  - "FileSystemWatcher (classe), exemples"
  - "surveiller les événements du système de fichiers"
ms.assetid: 207a3069-e63d-417e-8b56-00ab44f29c52
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: surveiller les modifications de syst&#232;me de fichiers (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise <xref:System.IO.FileSystemWatcher> pour s'inscrire aux événements qui correspondent aux fichiers créés, modifiés, supprimés ou renommés.  Plutôt que d'appeler régulièrement un répertoire pour connaître les modifications apportées aux fichiers, vous pouvez utiliser la classe <xref:System.IO.FileSystemWatcher> afin de déclencher des événements lorsqu'une modification est détectée.  
  
## Exemple  
  
```  
// monitor_fs.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::IO;  
  
ref class FSEventHandler  
{  
public:  
    void OnChanged (Object^ source, FileSystemEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} {1}",   
               e->FullPath, e->ChangeType);  
    }  
    void OnRenamed(Object^ source, RenamedEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} renamed to {1}",   
                e->OldFullPath, e->FullPath);  
    }  
};  
  
int main()  
{  
   array<String^>^ args = Environment::GetCommandLineArgs();  
  
   if(args->Length < 2)  
   {  
      Console::WriteLine("Usage: Watcher.exe <directory>");  
      return -1;  
   }  
  
   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );  
   fsWatcher->Path = args[1];  
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>   
              (NotifyFilters::FileName |   
               NotifyFilters::Attributes |   
               NotifyFilters::LastAccess |   
               NotifyFilters::LastWrite |   
               NotifyFilters::Security |   
               NotifyFilters::Size );  
  
    FSEventHandler^ handler = gcnew FSEventHandler();   
    fsWatcher->Changed += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Created += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Deleted += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Renamed += gcnew RenamedEventHandler(   
            handler, &FSEventHandler::OnRenamed);  
  
    fsWatcher->EnableRaisingEvents = true;  
  
    Console::WriteLine("Press Enter to quit the sample.");  
    Console::ReadLine( );  
}  
```  
  
## Voir aussi  
 [Espace de noms System.IO](https://msdn.microsoft.com/en-us/library/system.io.aspx)   
 [Fichier et flux de données E\/S](../Topic/File%20and%20Stream%20I-O.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
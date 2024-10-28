# BigFix Unique Client Setting Values Query

**Description**: This query finds unique client setting values for the BES Client. It provides the client setting and the number of iterations (i.e., the number of clients with that setting value).

---

## Query

```bigfix
(
(( substring before "|" of item 0 of it) as string)
 & "," & (( substring after "|" of item 0 of it) as string) 
 & "," & ((item 1 of it) as string)
)
of
(
(it, multiplicity of it) of unique values of ((name of it & "|" & ((value of it) as string)) of client settings whose (name of it starts with "_BES" and (1=1)) of it) of bes computers whose (true)
)
```

---

## Example Results

| Client Setting                                    | Value                                                                                                   | Count |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------|-------|
1     |
| _BESClient_ArchiveManager_FileSet-cdtClientLogs   | D:\Program Files (x86)\BigFix Enterprise\BES Console\BESClientDeploy\ClientLogs                         | 1     |
| _BESClient_ArchiveManager_FileSet-cdtMainLog      | D:\Program Files (x86)\BigFix Enterprise\BES Console\BESClientDeploy\BESClientDeployTool.log            | 1     |
| _BESClient_ArchiveManager_FileSet-client          | D:\Program Files (x86)\BigFix Enterprise\BES Client\__BESData\BES Support\__besdiag\*.*                 | 1     |
| _BESClient_ArchiveManager_FileSet-logs            | C:\Program Files (x86)\BigFix Enterprise\BES Client\__BESData\actionsite\..\__Global\Logs\*.*           | 1     |
| _BESClient_ArchiveManager_FileSet-logs            | D:\Program Files (x86)\BigFix Enterprise\BES Client\__BESData\actionsite\..\__Global\Logs\*.*           | 1     |
| _BESClient_ArchiveManager_FileSet-relaylog        | D:\Program Files (x86)\BigFix Enterprise\BES Server\BESRelay.log                                       | 1     |
| _BESClient_ArchiveManager_LastArchive             | 03aeadbd595442e9ecb585ca3e87e66d749d6aaca80dbebd670f61c2cff35be7                                        | 1     |
| _BESClient_ArchiveManager_MaxArchiveSize          | 209715200                                                                                               | 5     |
| _BESClient_Comm_CommandPollEnable                 | 1                                                                                                       | 7     |
| _BESClient_Comm_CommandPollIntervalSeconds        | 600                                                                                                     | 7     |
| _BESClient_ComputerType                           | Server                                                                                                  | 3     |
| _BESClient_Log_MaxSize                            | 1024000                                                                                                 | 7     |
| _BESRelay_HTTPServer_LogFilePath                  | D:\Program Files (x86)\BigFix Enterprise\BES Server\BESRelay.log                                       | 1     |
| _BESRelay_HTTPServer_PortNumber                   | 52311                                                                                                   | 1     |
| _BESRelay_HTTPServer_ServerRootPath               | D:\Program Files (x86)\BigFix Enterprise\BES Server\wwwrootbes\                                       | 1     |
| _BESRelay_UploadManager_BufferDirectory           | D:\Program Files (x86)\BigFix Enterprise\BES Server\UploadManagerData\BufferDir                         | 1     |

Etc..

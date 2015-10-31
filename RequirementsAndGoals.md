# Requirements And Goals #
  1. Find previously unknown security vulnerabilities
  1. Framework should be open and extendable
  1. Framework should provide support for multiple host and guest platforms
  1. Framework should take advantage of virtualization technology
  1. Framework should support automated crash analysis
  1. Framework should support code coverage analysis
  1. Framework should support fuzzing of multiple applications and multiple protocols
  1. The distributed protocol for the framework should provide configuration managment, polling, error recovery and security (confidentiality, avalibility, integrity).
  1. Core framework code shall be devleoped in Python
  1. Automation should be a top priority
  1. Provide good support for network elasticity (nodes being added and deleted)
  1. Framwork should have minimal user interaction
  1. Anyone should be able to join and participate
  1. Mutations, fuzzers, mutexes, etc.. should be gathered or derived by knowledable security experts.
  1. Framework should support multiple fuzzers


# Technical Requirements #
  1. Clients will be virtualized and will use the Open Virtualization Format
  1. Unique crashes should be reported to the server. Files that caused the unique crash should be uploaded to the server.
  1. Server shall use MySQL
  1. The database should store the user's identification along with the results the user has submitted.
  1. VPN tunnels will be used to provide CIA for users and the server
  1. VPN technology should adhear to the IPMEIR standards defined by the NSA ( http://www.nsa.gov/ia/_files/IPMEIR_IS100Core_pdfR1.pdf )
  1. Network error recovery will be provided by IPMEIR ORPHRC feature
  1. Authentication should use certificates
  1. To protect against outsider and insider threats IP allow lists should be created and altered if necessary

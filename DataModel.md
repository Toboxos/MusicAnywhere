# Playlist
Eine Playlist hat einen Namen
Eine Playlist hat eine textuelle Beschreibung
Eine Playlist hat einen eindeutigen Identifier
Eine Playlist enthält eine beliebige Anzahl Songs
Eine Playlist gehört immer zu einem User

# Song
Ein Song hat einen eindeutigen Identifier
Ein Song kommt von einer Platform
Von der Platform kommen folgende Daten:
 - Name
 - Dauer
 - Thumbnail

# User
Ein User hat einen einzigartigen & eindeutigen Namen
Ein User hat ein Profilbild
Ein User hat mindestens eine oder mehr verknüpfte Platformen
Ein User hat beliebig viele Playlisten

# Warteschlange
Eine Warteschlänge enthält eine Liste von Songs in der Reihenfolge, in der diese gespielt werden.

# Datendiagramm
@startuml
card playlist [
  Playlist
  ====
  uid : UUID
  name : String
  description : String
]

card user [
  User
  ====
  name : String
  image : Base64Data
]

card song [
  Song
  ====
  id : String
  / name : String
  / duration : Seconds
  / thumbnail : ImageData
]

card api_key [
  Platform API_KEY
  ====
  api_key : Data
]

api_key "1..*" --* "1" user
playlist "*" --- "1" user
song "*" --* "*" playlist
@enduml


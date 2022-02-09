################################################################################################
###################################################
Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?
###################################################

::::::::::::2.7.4 :010 > Album.count

   (0.4ms)  SELECT COUNT(*) FROM "albums"
 => 347



################################################################################################
###################################################
Qui est l'auteur de la chanson "White Room" ?
###################################################

::::::::::::2.7.4 :008 > my_track = Track.where(title: "White Room")

  Track Load (0.2ms)  SELECT  "tracks".* FROM "tracks" WHERE "tracks"."title" = ? LIMIT ?  [["title", "White Room"], ["LIMIT", 11]]
 => #<ActiveRecord::Relation [#<Track id: 505, title: "White Room", album: "The Cream Of Clapton", artist: "Eric Clapton", duration: 301583, size: 9872606...

::::::::::::2.7.4 :009 > tp Track.all

505 | White Room                     | The Cream Of Clapton           | Eric Clapton  



################################################################################################
###################################################
Quelle chanson dure exactement 188133 milliseconds ?
###################################################

::::::::::::2.7.4 :012 > my_track = Track.where(duration: 188133)

  Track Load (0.3ms)  SELECT  "tracks".* FROM "tracks" WHERE "tracks"."duration" = ? LIMIT ?  [["duration", 188133], ["LIMIT", 11]]
 => #<ActiveRecord::Relation [#<Track id: 40, title: "Perfect", album: "Jagged Little Pill", artist: "Alanis Morissette", duration: 188133, size: 6145404,...



################################################################################################
###################################################
Quel groupe a sorti l'album "Use Your Illusion II" ?
###################################################

::::::::::::2.7.4 :014 > my_album = Album.where(title: "Use Your Illusion II")

  Album Load (0.5ms)  SELECT  "albums".* FROM "albums" WHERE "albums"."title" = ? LIMIT ?  [["title", "Use Your Illusion II"], ["LIMIT", 11]]
 => #<ActiveRecord::Relation [#<Album id: 92, title: "Use Your Illusion II", artist: "Guns N Roses", created_at: "2022-02-09 21:31:54", updated_at: "2022-...



################################################################################################
###################################################
Combien y a t'il d'albums dont le titre contient "Great" ? 
###################################################


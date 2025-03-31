Spjallrómur DB
===

This is a Pyannote database configuration for Spjallrómur.
It includes a train, development and test split of the data as well as a single conversation gold standard annotation.

ATT! This is still a work in progress.


How to use
===

Download Spjallrómur from [Clarin](https://repository.clarin.is/repository/xmlui/handle/20.500.12537/187) and unzip in this location.
You can use the following ´curl´ command:
´´´
curl --remote-name-all https://repository.clarin.is/repository/xmlui/bitstream/handle/20.500.12537/187{/spjallromur_README.txt,/spjallromur_full_conversations.zip}
´´´

Load Spjallrómur with pyannote:

´´´
from pyannote.database import registry, FileFinder

registry.load_database("data/Spjallromur-pyannote/database.yml")
dataset = registry.get_protocol("Spjallromur.SpeakerDiarization.words_and_vocal_sounds", preprocessors={"audio": FileFinder()})
´´´
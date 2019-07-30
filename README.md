### dejavu
---
https://github.com/worldveil/dejavu

```py
from dejavu import Dejavu
config = {
  "database": {
    "host": "127.0.0.1",
    "user": "root",
    "passwd": <password above>,
    "db": <name of the database you created above>,
  }
}
djv = Dejavu(config)

djv.fingerprint_directory("va_us_top_40/mp3", [".mp3"], 3)

print djv.db.get_num_fingerprints()

from dejavu import Dejavu
config = {
  "database": {
    "host": "127.0.0.1",
    "user": "root",
    "passwd": "Password123",
    "db": "dejavu_db",
  },
  "database_type": "mysql",
  "fingerprint": 10
}
djv = Dejavu(config)

FINGERPRINT_REDUCTION = 30
PEAK_SORT = False
DEFAULT_OVERLAP_RATIO = 0.4
DEFAULT_AMP_MIN = 15
PEAK_NEIGHBORHOOD_SIZE = 30

from dejavu.recognize import FileRecognier
song = djv.recognize(FileRecognizer, "va_us_top_40/wav/Mirrors - Justin Timberlake.wav")

from dejavu.recognize import MicrohoneRecognizer
song = djv.recognize(MicrophoneRecognizer, seconds=10)
```

```sh
mysql -u root -p
CREATE DATABASE IF NOT EXISTS dejavu;
git clone https://github.com/worldeil/dejavu.git ./dejavu
python example.py

python dejavu.py --recognize file sometrack.wav
python dejavu.py --recognize mic 10

rm -rf ./results ./temp_audio
python dejavu.py --fingerprint ./mp3/ mp3
python run_tests.py \
  --secs 5 \
  --temp ./temp_audio \
  --log-file ./reesult/dejavu-test.log \
  --padding 8 \
  --seed 42 \
  --results ./results \
  ./mp3
```

```
```



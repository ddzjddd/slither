# Slither, Plugin Example

This repository contains an example of plugin for Slither.

See the [detector documentation](https://github.com/trailofbits/slither/wiki/Adding-a-new-detector).

## Architecture

- `setup.py`: Contain the plugin information
- `slither_my_plugin/__init__.py`: Contain `make_plugin()`. The function must return the list of new detectors and printers
- `slither_my_plugin/detectors/example.py`: Detector plugin skeleton.

Once these files are updated with your plugin, you can install it:
```bash
python setup.py develop
```

We recommend to use a Python virtual environment (for example: [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/)).


通过命令：python3 -c "import slither; import os; print(os.path.dirname(slither.__file__))"
确认路径：/root/slither_venv/lib/python3.12/site-packages/slither/detectors
将setup.py、slither_my_plugin拷贝至该目录下，进入slither_my_plugin，修改其中的__init__.py：
  from slither_my_plugin.detectors.AmmmManipulablePriceDetector import AmmmManipulablePriceDetector
  plugin_detectors = [AmmmManipulablePriceDetector]
AmmmManipulablePriceDetector为具体的自定义检测器

  

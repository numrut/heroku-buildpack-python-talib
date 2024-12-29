# Heroku Buildpack: Python + TA-Lib

This buildpack installs the [TA-Lib C library](https://ta-lib.org/) and the corresponding Python wrapper for technical analysis in financial applications.

## Usage

This buildpack should be used in conjunction with the [official Heroku Python buildpack](https://github.com/heroku/heroku-buildpack-python). Ensure the Python buildpack is listed first.

```
~ $ heroku buildpacks:add --index 1 heroku/python
~ $ heroku buildpacks:add --index 2 https://github.com/t-shah/heroku-buildpack-python-talib.git
```

- **Do not include TA-Lib in requirements.txt.**
  - The buildpack installs the TA-Lib Python wrapper automatically.

## Debugging

If the build fails, check the logs for detailed error messages:

- **Common issues:**
  - Missing build tools (`gcc`, `make`).
  - Network issues during source code download.
 
## Configuration

- **Installation directory:** The buildpack installs TA-Lib to `/app/.heroku/vendor/ta-lib`.
- **Environment variables:**
  - `LD_LIBRARY_PATH`: Ensures the linker can locate `libta_lib.so`.
  - `CFLAGS`: Points to the TA-Lib headers.

## Compatibility

- **Heroku stacks:**
  - `heroku-20`
  - `heroku-22`
- **Python versions:**
  - Compatible with Python 3.7 - 3.10.

## Troubleshooting

1. **Build Errors:**
   - Check the output of `./configure`, `make`, and `make install` for issues.
   - Ensure that `requirements.txt` excludes `TA-Lib`.

2. **Library Not Found:**
   - Verify that `libta_lib.so` exists in `/app/.heroku/vendor/ta-lib/lib`.

3. **Python Version Compatibility:**
   - Confirm the Python version used by your app matches the supported versions for TA-Lib.

## Contributions

Feel free to open an issue or PR to improve this buildpack!

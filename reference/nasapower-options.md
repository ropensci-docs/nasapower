# nasapower Options

The behaviour of certain nasapower functions can be controlled through
package-level options. These are set via
[`base::options()`](https://rdrr.io/r/base/options.html) and retrieved
internally using
[`base::getOption()`](https://rdrr.io/r/base/options.html). All options
have sensible defaults and do not need to be set for normal use.

Options can be set for a single session:

    options(nasapower.timeout = 60L)

Or persistently across sessions by adding them to your `.Rprofile`:

    # ~/.Rprofile
    options(
      nasapower.timeout         = 60L,
      nasapower.timeout.connect = 10L,
      nasapower.max_tries       = 3L
    )

## Options

- `nasapower.timeout`:

  Maximum time in seconds to wait for data to be transferred from the
  POWER API before the request is aborted. This controls the overall
  transfer timeout, not the time to establish a connection (see
  `nasapower.timeout.connect`).

      Should be a single positive number. Non-integer values are coerced to
      integer. If an invalid value is supplied a warning is issued and the
      default is used.

      Default: `10L`.

      Increase this if you are retrieving large regional datasets or are on a
      slow connection.

- `nasapower.timeout.connect`:

  Maximum time in seconds to wait for a connection to the POWER API to
  be established before the request is aborted. A connection that takes
  longer than this is unlikely to succeed, so this is intentionally kept
  shorter than `nasapower.timeout`.

      Should be a single positive number. Non-integer values are coerced to
      integer. If an invalid value is supplied a warning is issued and the
      default is used.

      Default: `5L`.

- `nasapower.max_tries`:

  Maximum number of times a failed request will be retried before an
  error is thrown. Retries are handled automatically by the underlying
  HTTP client and apply to transient failures (e.g., network timeouts,
  HTTP 429 or 503 responses).

      Should be a single positive integer >= 1. A value of `1L` disables
      retries. If an invalid value is supplied a warning is issued and the
      default is used.

      Default: `6L`.

      Consider reducing this in automated pipelines where you would prefer to
      fail fast and handle retries externally.

## Cumulative wait time

The worst-case time before an error is surfaced to the user is
approximately:

    nasapower.max_tries * nasapower.timeout

With defaults (`6L * 10L`) this is roughly 60 seconds. If you increase
either value, be aware of the combined effect on how long your code may
block.

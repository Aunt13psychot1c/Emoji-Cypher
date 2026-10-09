# Emoji Cipher

Turn any message into emoji and back. Built by Aunt13Psychotic / Queen of Chaos.

Open `index.html` in a browser. That's it. No build step, no dependencies, no server.

## How it works

Every character gets **three different emoji**, picked at random each time it's encoded. Type `HELLO` twice and you get two different-looking strings that both decode back to `HELLO`.

The character set covers A-Z, 0-9, space, and `. , ! ? ' " - : ; ( ) /`. Spaces are encoded too, so nobody can read word lengths off the output. Anything outside the set (line breaks, other alphabets) passes through untouched.

## The password key

Leave the password blank and you get the **open cipher** — anyone with this tool can decode it.

Put a word in and the entire emoji alphabet gets reshuffled by a seeded PRNG keyed to that word. Same word in, same shuffle out, every time, on any device. Different word, completely different alphabet. Without the exact password, the key panel is useless to them.

The shuffle is deterministic (xmur3 seed into an sfc32 generator), so two people with the same password always build the same mapping without ever exchanging the mapping itself.

## Hosting it

It's one self-contained file. Drop it anywhere that serves static HTML.

For GitHub Pages: push this repo, then Settings → Pages → Deploy from branch → `main` / root. The page comes up at `https://<user>.github.io/<repo>/`.

## Not a security tool

This is a substitution cipher wearing emoji. It's fun, it's obscure, and a determined person with enough ciphertext can crack it with frequency analysis like any substitution cipher. Use it for puzzles, server games and passing notes. Don't use it for anything that actually needs to stay secret.

## License

MIT — see LICENSE.

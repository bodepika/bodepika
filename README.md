#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# Subtle Hacker Intro — aesthetic only.
# Credits: vibes borrowed from bonfires and terminal goth.
# Not a tool. Does NOT execute or teach any offensive action.
# Use as README garnish or profile script.

import time
import random
import sys
from datetime import datetime

# ---- Config ----
TYPE_DELAY = 0.02
TITLE_DELAY = 0.06

# Subtle "tool" references (purely cosmetic)
TOOLBELT = [
    "nmap (desktop)",
    "netcat (pocket)",
    "john (forged-keys)",
    "hydra (brittle-locks)",
    "metasploit (ripples)",
    "tcpdump (echoes)",
]

TAGLINES = [
    "quietly enumerating curiosities...",
    "listening to packet ghosts (metaphorically).",
    "the network hums, you write.",
    "brushing the edge of the abyss — code, not chaos.",
    "logs are poems; commits are prayers.",
    "prepare to push. gently.",
]

ASCII_HEADER = r"""
  ____        _     _ _ _          _             
 / ___| _   _| |__ (_) (_) ___ ___| | ___  _ __  
 \___ \| | | | '_ \| | | |/ __/ _ \ |/ _ \| '_ \ 
  ___) | |_| | |_) | | | | (_|  __/ | (_) | | | |
 |____/ \__,_|_.__/|_|_|_|\___\___|_|\___/|_| |_|
"""

# ---- Utils ----
def slow_type(text, delay=TYPE_DELAY, newline=True):
    for ch in text:
        sys.stdout.write(ch)
        sys.stdout.flush()
        time.sleep(delay)
    if newline:
        sys.stdout.write("\n")
        sys.stdout.flush()

def header():
    slow_type(ASCII_HEADER, delay=0.001)
    slow_type("  — subtle profile intro  ·  aesthetic / non-destructive", TYPE_DELAY)
    slow_type(f"  {datetime.utcnow().strftime('%Y-%m-%d %H:%M:%S')} UTC", TYPE_DELAY)
    print()

def show_title():
    slow_type("~ quiet terminal ~", TITLE_DELAY)
    time.sleep(0.4)
    slow_type(random.choice(TAGLINES), TYPE_DELAY)
    print()

def show_toolbelt():
    slow_type("toolbelt: ", TYPE_DELAY, newline=False)
    for i, t in enumerate(TOOLBELT, start=1):
        # print tools in a minimal, non-sensational way
        sys.stdout.write(f"[{t}]")
        if i != len(TOOLBELT):
            sys.stdout.write(" · ")
        sys.stdout.flush()
        time.sleep(0.12)
    print("\n")

def fake_scan():
    # purely stylized output — not real scanning or instructive
    targets = ["localhost", "127.0.0.1", "devbox", "the-archive"]
    fingerprints = ["open-ish port", "closed (silenced)", "service: monologue", "sleeping daemon"]
    slow_type("> initiating harmless echo...", TYPE_DELAY)
    time.sleep(0.6)
    for t in targets:
        slow_type(f"[{t}] probing status", TYPE_DELAY)
        time.sleep(0.25)
        lines = random.randint(2,4)
        for _ in range(lines):
            ts = datetime.utcnow().strftime("%H:%M:%S")
            fp = random.choice(fingerprints)
            slow_type(f"  {ts}  — {fp}", TYPE_DELAY)
        time.sleep(0.18)
    slow_type("> echo complete. nothing harmed, only aesthetics.", TYPE_DELAY)
    print()

def footer():
    slow_type("» keep your commits tidy. comments are for the brave.", TYPE_DELAY)
    slow_type("» README-ready: add a snippet linking to this script.", TYPE_DELAY)
    slow_type("— end of subtle session —", TYPE_DELAY)

def main():
    header()
    show_title()
    show_toolbelt()
    fake_scan()
    footer()

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        slow_type("\n» session aborted. flame preserved.")

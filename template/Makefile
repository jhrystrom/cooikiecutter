.PHONY: install lint test

install:
	uv sync

lint:
	uv run ruff check --fix .
	uv run ruff format --check .
	uv run ty check .

test:
	uv run pytest

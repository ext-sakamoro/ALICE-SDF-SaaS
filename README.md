# ALICE-SDF SaaS

SDF 3D geometry generation and mesh conversion API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-SDF |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/evaluate` | SDF式評価・メッシュ生成 |
| `POST /api/v1/boolean` | SDF CSGブーリアン演算 |
| `GET  /api/v1/primitives` | 基本プリミティブ一覧 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
